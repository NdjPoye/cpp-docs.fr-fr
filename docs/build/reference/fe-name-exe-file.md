---
title: -Fe (nom de fichier EXE) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /fe
dev_langs: C++
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 83965ef2bf64f77dbcb1eb9832e7178c30260d16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fe-name-exe-file"></a>/Fe (Nom de fichier EXE)
Spécifie un nom et un répertoire pour le fichier .exe ou DLL créé par le compilateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Fepathname  
```  
  
## <a name="remarks"></a>Notes  
 Sans cette option, le compilateur donne au fichier un nom par défaut en utilisant le nom de base du premier fichier source ou un objet spécifié sur la ligne de commande et de l’extension .exe ou .dll.  
  
 Si vous spécifiez la[/c (compiler sans liaison)](../../build/reference/c-compile-without-linking.md), pour compiler sans liaison, **/Fe** n’a aucun effet.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **l’éditeur de liens** dossier.  
  
3.  Cliquez sur le **général**page de propriétés.  
  
4.  Modifier la **fichier de sortie** propriété.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.  
  
## <a name="example"></a>Exemple  
 La ligne de commande suivante compile et lie tous les fichiers de code source C dans le répertoire actif. Le fichier exécutable résultant est nommé PROCESS.exe et est créé dans le répertoire C:\BIN.  
  
```  
CL /FeC:\BIN\PROCESS *.C  
```  
  
## <a name="example"></a>Exemple  
 La ligne de commande suivante crée un fichier exécutable dans `C:\BIN` avec le même nom que le premier fichier source ou un objet :  
  
```  
CL /FeC:\BIN\ *.C  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fichier de sortie (/ F) Options](../../build/reference/output-file-f-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des Options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Spécification du nom de chemin](../../build/reference/specifying-the-pathname.md)