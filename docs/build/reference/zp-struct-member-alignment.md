---
title: -Zp (alignement des membres de la structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
dev_langs:
- C++
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d387e0ab020e96afb3e2975b5c8686b668cbc10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="zp-struct-member-alignment"></a>/Zp (Alignement des membres de la structure)
Contrôle la façon dont les membres d’une structure sont compressés en mémoire et spécifie la même compression pour toutes les structures dans un module.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Zp[1|2|4|8|16]  
```  
  
## <a name="remarks"></a>Notes  
 Lorsque vous spécifiez cette option, chaque membre de structure après le premier est stocké sur la taille du type du membre ou `n`-limites d’octets (où `n` est 1, 2, 4, 8 ou 16), plus petite étant retenue.  
  
 Les valeurs disponibles sont décrits dans le tableau suivant.  
  
 1  
 Compresse les structures sur des limites de 1 octet. Identique à **/Zp**.  
  
 2  
 Compresse les structures sur des limites de 2 octets.  
  
 4  
 Compresse les structures sur des limites de 4 octets.  
  
 8  
 Compresse les structures sur des limites de 8 octets (par défaut).  
  
 16  
 Compresse les structures sur des limites de 16 octets.  
  
 Vous ne devez pas utiliser cette option sauf si vous avez des exigences d’alignement spécifique.  
  
 Vous pouvez également utiliser [pack](../../preprocessor/pack.md) à la compression de structure de contrôle. Pour plus d'informations sur l'alignement, consultez :  
  
-   [align](../../cpp/align-cpp.md)  
  
-   [__alignof, opérateur](../../cpp/alignof-operator.md)  
  
-   [__unaligned](../../cpp/unaligned.md)  
  
-   [Exemples d’alignement de Structure](../../build/examples-of-structure-alignment.md) (x64 spécifique)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **C/C++** .  
  
3.  Cliquez sur le **génération de Code** page de propriétés.  
  
4.  Modifier la **alignement des membres de Struct** propriété.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)