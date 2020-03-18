---
title: Directivas de configuración de invitado
description: Utilice Cloud Adoption Framework para aprender a usar la extensión Configuración de invitado de Azure Policy para auditar la configuración en una máquina virtual de Azure.
author: BrianBlanchard
ms.author: brblanch
ms.date: 05/10/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: 73373e5cc56ef7e5804151171a22ad9f541f1cd3
ms.sourcegitcommit: 959cb0f63e4fe2d01fec2b820b8237e98599d14f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2020
ms.locfileid: "79094689"
---
# <a name="guest-configuration-policy"></a>Directivas de configuración de invitado

La extensión [Configuración de invitado](https://docs.microsoft.com/azure/governance/policy/concepts/guest-configuration) de Azure Policy se puede usar para auditar la configuración en una máquina virtual. Configuración de invitado solo se admite de momento en máquinas virtuales de Azure.

Para encontrar la lista de directivas de configuración de invitado, busque la categoría "Configuración de invitado" en la página del portal de Azure Policy. También puede ejecutar este cmdlet en una ventana de PowerShell para encontrar la lista:

```powershell
Get-AzPolicySetDefinition | where-object {$_.Properties.metadata.category -eq "Guest Configuration"}
```

> [!NOTE]
> La funcionalidad de configuración de invitado se actualiza periódicamente para admitir conjuntos de directivas adicionales. Compruebe periódicamente si hay nuevas directivas admitidas y evalúe si le resultarán útiles.

<!-- TODO: Update these links when available. 

By default, we recommend that you enable the following policies:

- [Preview]: Audit to verify that password-security settings are correct on Linux and Windows machines.
- Audit to verify that certificates are not nearing expiration on Windows VMs.

-->

## <a name="deployment"></a>Implementación

Utilice el siguiente script de ejemplo de PowerShell para implementar estas directivas para llevar a cabo lo siguiente:

- Compruebe que la configuración de seguridad de las contraseñas en equipos Windows y Linux está establecida correctamente.
- Compruebe que los certificados no están próximos a expirar en máquinas virtuales Windows.

 Antes de ejecutar este script, utilice el cmdlet [Connect-AzAccount](https://docs.microsoft.com/powershell/module/az.accounts/connect-azaccount?view=azps-2.1.0) para iniciar sesión. Al ejecutar el script, debe proporcionar el nombre de la suscripción a la que quiere aplicar las directivas.

```powershell

    #Assign Guest Configuration policy.
    param (
        [Parameter(Mandatory=$true)]
        [string]$SubscriptionName
    )

    $Subscription = Get-AzSubscription -SubscriptionName $SubscriptionName
    $scope = "/subscriptions/" + $Subscription.Id

    $PasswordPolicy = Get-AzPolicySetDefinition -Name "3fa7cbf5-c0a4-4a59-85a5-cca4d996d5a6"
    $CertExpirePolicy = Get-AzPolicySetDefinition -Name "b6f5e05c-0aaa-4337-8dd4-357c399d12ae"

    New-AzPolicyAssignment -Name "PasswordPolicy" -DisplayName "[Preview]: Audit that password security settings are set correctly inside Linux and Windows machines" -Scope $scope -PolicySetDefinition $PasswordPolicy -AssignIdentity -Location eastus

    New-AzPolicyAssignment -Name "CertExpirePolicy" -DisplayName "[Preview]: Audit that certificates are not expiring on Windows VMs" -Scope $scope -PolicySetDefinition $CertExpirePolicy -AssignIdentity -Location eastus

```

## <a name="next-steps"></a>Pasos siguientes

Aprenda a [Habilitar el seguimiento y las alertas de los cambios críticos](./enable-tracking-alerting.md) de archivos, servicios, software y el registro.

> [!div class="nextstepaction"]
> [Habilitar el seguimiento y las alertas de los cambios críticos](./enable-tracking-alerting.md)
