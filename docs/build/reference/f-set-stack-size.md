---
title: "-F (définir la taille de pile) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /f
dev_langs:
- C++
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b464a4fb28eb83ef0570416d0cb18fd8f965e0a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="f-set-stack-size"></a>/F (Définir la taille de pile)
Définit la taille de pile du programme en octets.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/F number  
```  
  
## <a name="arguments"></a>Arguments  
 `number`  
 La taille de pile en octets.  
  
## <a name="remarks"></a>Notes  
 Sans cette option, la taille de pile par défaut est 1 Mo. Le `number` argument peut être en notation décimale ou en langage C. L’argument de plage de 1 à la taille de pile maximale acceptée par l’éditeur de liens. L’éditeur de liens arrondit la valeur spécifiée aux plus proche de 4 octets. L’espace entre **/F** et `number` est facultatif.  
  
 Vous devrez peut-être augmenter la taille de pile si votre programme obtient les messages de débordement de pile.  
  
 Vous pouvez également définir la taille de pile :  
  
-   À l’aide de la **/pile** option de l’éditeur de liens. Pour plus d’informations, consultez [/pile](../../build/reference/stack.md).  
  
-   À l’aide de EDITBIN sur le fichier .exe. Pour plus d’informations, consultez [référence EDITBIN](../../build/reference/editbin-reference.md).  
  
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