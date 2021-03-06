---
title: runtime_checks | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
dev_langs:
- C++
helpviewer_keywords:
- runtime_checks pragma
- pragmas, runtime_checks
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 817afaff738b2528bd165e814517c8399cd8a151
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="runtimechecks"></a>runtime_checks
Désactive ou restaure les paramètres [/RTC](../build/reference/rtc-run-time-error-checks.md) .  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
#pragma runtime_checks( "[runtime_checks]", {restore | off} )  
```  
  
## <a name="remarks"></a>Notes  
 Vous ne pouvez pas activer un contrôle à l'exécution qui n'a pas été activé via une option du compilateur. Par exemple, si vous ne spécifiez aucun paramètre /RTC, la spécification de `#pragma runtime_checks( "s", restore)` n'active pas la vérification du frame de pile.  
  
 Le pragma **runtime_checks** doit apparaître à l'extérieur d'une fonction et prend effet à la première fonction définie après sa détection. Les arguments **restore** et **off** activent ou désactivent les options spécifiées dans *runtime_checks* .  
  
 Le pragma *runtime_checks* peut être égal à zéro ou plusieurs des paramètres indiqués dans le tableau suivant.  
  
### <a name="parameters-of-the-runtimechecks-pragma"></a>Paramètres du pragma runtime_checks  
  
|Paramètre(s)|Type de contrôle à l'exécution|  
|--------------------|-----------------------------|  
|**s**|Active la vérification de pile (frame).|  
|**c**|Signale quand une valeur est assignée à un type de données plus petit qui se traduit par une perte de données.|  
|**u**|Signale quand une variable est utilisée avant d'être définie.|  
  
 Ce sont les mêmes lettres que celles utilisées avec l'option du compilateur /RTC. Par exemple :  
  
```  
#pragma runtime_checks( "sc", restore )  
```  
  
 L'utilisation du pragma **runtime_checks** avec la chaîne vide (**""**) est une forme particulière de la directive :  
  
-   Lorsque vous utilisez le paramètre **off** , il désactive les contrôles d'erreurs à l'exécution, répertoriés dans le tableau ci-dessus.  
  
-   Lorsque vous utilisez le paramètre **restore** , il réinitialise les contrôles d'erreurs à l'exécution à ceux que vous avez spécifiés avec l'option du compilateur /RTC.  
  
```  
#pragma runtime_checks( "", off )  
.  
.  
.  
#pragma runtime_checks( "", restore )   
```  
  
## <a name="see-also"></a>Voir aussi  
 [Directives pragma et mot clé _Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
