---
title: "Comment&#160;: utiliser un visualiseur | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.dataviewer"
  - "vs.debug.stringviewer"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "débogueur, visualiseurs"
  - "visualiseurs, à propos des visualiseurs"
ms.assetid: d2611385-0134-4387-8c5a-979fe625a462
caps.latest.revision: 37
caps.handback.revision: 37
ms.author: "susanno"
manager: "douge"
---
# Comment&#160;: utiliser un visualiseur
Vous pouvez utiliser un visualiseur afin d'afficher le contenu d'une variable ou d'un objet de façon explicite pour le type de données.  Vous pouvez utiliser des visualiseurs depuis les **DataTips**, une fenêtre **Espion**, la fenêtre **Automatique** ou la fenêtre **Variables locales**.  
  
 Les visualiseurs ne sont pas pris en charge sur le Compact Framework.  
  
> [!NOTE]
>  Dans les applications de **Store**, seul les visualiseurs HTML, XML, JSON et de texte standard sont pris en charge.  Les visualiseurs personnalisés \(créés par l'utilisateur\) ne sont pas pris en charge.  
  
### Pour ouvrir un visualiseur  
  
1.  Cliquez sur l'icône de loupe située en regard d'un nom de variable dans les **DataTips**, dans la fenêtre **Espion**, ou dans la fenêtre **Automatique**, **Variables locales** ou **Espion express**.  
  
     Une liste de visualiseurs s'affiche.  
  
2.  Cliquez sur le visualiseur à utiliser.  
  
### Pour utiliser un visualiseur pour le code managé pendant le débogage distant  
  
-   Copiez la DLL de visualiseur vers l'ordinateur distant avant de démarrer la session de débogage.  
  
     Le chemin d'accès à la DLL doit être le même sur les ordinateurs local et distant.  Ce chemin d'accès peut correspondre à l'un ou l'autre des emplacements suivants :  
  
     *Chemin d'accès de l'installation de Visual Studio*`\Common7\Packages\Debugger\Visualizers`  
  
     ou  
  
     `My Documents\Visual Studio 2010\Visualizers`*Version de Visual Studio*`\Visualizers`  
  
## Voir aussi  
 [Visualiseurs](../Topic/Create%20Custom%20Visualizers%20of%20Data.md)   
 [Comment : installer un visualiseur](../Topic/How%20to:%20Install%20a%20Visualizer.md)   
 [Comment : écrire un visualiseur](../Topic/How%20to:%20Write%20a%20Visualizer.md)   
 [Afficher les valeurs des données dans les conseils de données](../Topic/View%20data%20values%20in%20Data%20Tips%20%20in%20the%20code%20editor.md)