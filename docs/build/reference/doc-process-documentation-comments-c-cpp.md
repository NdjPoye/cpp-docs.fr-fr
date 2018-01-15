---
title: -doc (traiter les commentaires de Documentation) (C/C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- /doc
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
dev_langs: C++
helpviewer_keywords:
- /doc compiler option [C++]
- comments, C++ code
- XML documentation, comments in source files
- -doc compiler option [C++]
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8737c0e33d33fe062d9a07f18d9005e58463f5b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="doc-process-documentation-comments-cc"></a>/doc (Traiter les commentaires de documentation) (C/C++)
Indique au compilateur de traiter les commentaires de documentation dans les fichiers de code source et pour créer un fichier .xdc pour chaque fichier de code source qui a des commentaires de documentation.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/doc[name]  
```  
  
## <a name="arguments"></a>Arguments  
 `name`  
 Le nom du fichier .xdc que le compilateur créera. Valide uniquement lorsqu’un fichier .cpp est passé dans la compilation.  
  
## <a name="remarks"></a>Notes  
 Les fichiers .xdc sont traités dans un fichier .xml avec xdcmake.exe. Pour plus d’informations, consultez [XDCMake référence](../../ide/xdcmake-reference.md).  
  
 Vous pouvez ajouter des commentaires de documentation à vos fichiers de code source. Pour plus d’informations, consultez [balises recommandées pour commentaires de Documentation](../../ide/recommended-tags-for-documentation-comments-visual-cpp.md).  
  
 Pour utiliser le fichier .xml généré avec IntelliSense, vérifiez le nom de fichier du fichier .xml identique à l’assembly que vous souhaitez prendre en charge et placez le fichier .xml est dans le même répertoire que l’assembly. Lors de l’assembly est référencé dans le projet Visual Studio, le fichier .xml est également détecté. Pour plus d’informations, consultez [utilisation d’IntelliSense](/visualstudio/ide/using-intellisense) et [en fournissant des commentaires de Code XML](/visualstudio/ide/supplying-xml-code-comments).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Développez le **propriétés de Configuration** nœud.  
  
3.  Développez le **C/C++** nœud.  
  
4.  Sélectionnez le **fichiers de sortie** page de propriétés.  
  
5.  Modifier la **générer des fichiers de Documentation XML** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)