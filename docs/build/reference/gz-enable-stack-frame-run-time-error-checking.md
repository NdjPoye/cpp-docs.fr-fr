---
title: "-GZ (activer la pile des vérifications des erreurs d’exécution Frame) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /gz
dev_langs: C++
helpviewer_keywords:
- -GZ compiler option [C++]
- release-build errors
- /GZ compiler option [C++]
- GZ compiler option [C++]
- debug builds, catch release-build errors
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f3e4dc59154d64d79db0f4d15471b51ce67bed58
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="gz-enable-stack-frame-run-time-error-checking"></a>/GZ (Activer les vérifications des erreurs au moment de l'exécution pour le frame de pile)
Effectue les mêmes opérations que les [/RTC (vérifications des erreurs Run-Time)](../../build/reference/rtc-run-time-error-checks.md) option. Obsolète.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/GZ  
```  
  
## <a name="remarks"></a>Remarques  
 **GZ** doit uniquement être utilisée dans un code ([/Od (désactiver (débogage))](../../build/reference/od-disable-debug.md)) générer.  
  
 **GZ** est déconseillée depuis Visual Studio 2005 ; utilisez [/RTC (vérifications des erreurs Run-Time)](../../build/reference/rtc-run-time-error-checks.md) à la place. Pour obtenir la liste des options du compilateur déconseillées, consultez **déconseillées et supprimées des Options du compilateur** dans [Options du compilateur classées par catégorie](../../build/reference/compiler-options-listed-by-category.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **C/C++** .  
  
3.  Cliquez sur la page de propriétés **Ligne de commande** .  
  
4.  Tapez l'option de compilateur dans la zone **Options supplémentaires** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)