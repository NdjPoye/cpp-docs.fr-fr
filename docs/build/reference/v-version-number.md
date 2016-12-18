---
title: "/V (Num&#233;ro de version) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/v"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/V (option du compilateur C++)"
  - "incorporer des chaînes de version"
  - "V (option du compilateur C++)"
  - "-V (option du compilateur C++)"
  - "numéros de version, spécifier pour .obj"
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /V (Num&#233;ro de version)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Incorpore une chaîne de textedans le fichier .obj.  Déconseillé.  
  
## Syntaxe  
  
```  
/Vstring  
```  
  
## Arguments  
 `string`  
 Chaîne spécifiant le numéro de version ou la notice de copyright à incorporer dans un fichier .obj.  
  
## Notes  
 Cette chaînepeut étiqueter un fichier .obj avec un numéro de version ou une mention de droits d'auteur.  Les espaces ou les caractères de tabulation doivent être mis entre guillemets doubles \("\) s'ils font partie de la chaîne.  Une barre oblique inverse \(\\\) doit précéder les guillemets doubles si ceux\-ci font également partie de la chaîne.  L'espace entre **\/V** et `string` est facultatif.  
  
 Vous pouvez aussi utiliser [commentaire](../../preprocessor/comment-c-cpp.md) avec l'argument de type commentaire du compilateur pour incorporer le nom et le numéro de version du compilateur dans le fichier .obj.  
  
 L'option **\/V** est déconseillée ; **\/V** permet essentiellement de prendre en charge la génération de pilotes de périphérique virtuels \(VxD\) et cette opération n'est plus prise en charge par l'ensemble d'outils de [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)].  Pour plus d'informations, consultez [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/fr-fr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)