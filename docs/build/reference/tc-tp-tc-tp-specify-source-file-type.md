---
title: "-Tc, - Tp,-TC, - TP (spécifier le Type de fichier Source) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
dev_langs: C++
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
ms.assetid: 7d9d0a65-338b-427c-8b48-fff30e2f9d2b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 69ccd08967d386780744fb85476033430127ba3a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc, /Tp, /TC, /TP (Spécifier le type de fichier source)
Le **/Tc** option spécifie que `filename` est un fichier source C, même si elle n’a pas d’extension .c. Le **/Tp** option spécifie que `filename` est un fichier source C++, même si elle n’a pas l’extension .cpp ou .cxx. Un espace entre l’option et `filename` est facultatif. Chaque option spécifie un fichier ; Pour spécifier des fichiers supplémentaires, répétez l’option.  
  
 **/TC** et **/TP** sont des variantes globales de **/Tc** et **/Tp**. Ils indiquent au compilateur de traiter tous les fichiers nommés sur la ligne de commande en tant que fichiers sources C (**/TC**) ou des fichiers sources C++ (**/TP**), sans tenir compte de l’emplacement sur la ligne de commande par rapport à l’option. Ces options globales peuvent être substituées sur un seul fichier à l’aide de **/Tc** ou **/Tp**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Tcfilename  
/Tpfilename  
/TC  
/TP  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Un fichier source C ou C++.  
  
## <a name="remarks"></a>Notes  
 Par défaut, CL considère que les fichiers avec l’extension .c sont des fichiers sources C et les fichiers .cpp ou .cxx sont des fichiers sources C++.  
  
 Lorsque soit la **TC** ou **Tc** option est spécifiée, toute spécification de la [/Zc : (wchar_t est un Type natif)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) option est ignorée.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **C/C++** .  
  
3.  Cliquez sur le **avancé** page de propriétés.  
  
4.  Modifier la **compilation sous** propriété.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>.  
  
## <a name="examples"></a>Exemples  
 La ligne de commande CL suivante spécifie que MAIN.c, TEST.prg et COLLATE.prg sont tous les fichiers de code source C. CL ne reconnaîtra pas PRINT.prg.  
  
```  
CL MAIN.C /TcTEST.PRG /TcCOLLATE.PRG PRINT.PRG  
```  
  
 La ligne de commande CL suivante spécifie que TEST1.c, TEST2.cxx, TEST3.huh et TEST4.o sont compilés en tant que fichiers C++, et que TEST5.z est compilé en tant qu’un fichier C.  
  
```  
CL TEST1.C TEST2.CXX TEST3.HUH TEST4.O /Tc TEST5.Z /TP  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)