---
title: "Pages de propri&#233;t&#233;s HLSL&#160;: fichiers de sortie | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.FXCompilerTool.AssemblerOutput"
  - "VC.Project.FXCompilerTool.ObjectFileOutput"
  - "VC.Project.FXCompilerTool.HeaderFileOutput"
  - "VC.Project.FXCompilerTool.VariableName"
  - "VC.Project.FXCompilerTool.AssemblerOutputFile"
dev_langs: 
  - "C++"
ms.assetid: c5ba1e72-30de-43eb-a15a-5b0ae58e55c2
caps.latest.revision: 5
caps.handback.revision: 5
author: "BrianPeek"
ms.author: "brpeek"
manager: "ghogen"
---
# Pages de propri&#233;t&#233;s HLSL&#160;: fichiers de sortie
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour configurer les propriétés suivantes du compilateur de HLSL \(fxc.exe\), utilisez sa propriété **FICHIERS DE SORTIE** .  Pour plus d'informations sur l'accès à la page de propriétés **FICHIERS DE SORTIE** dans le dossier de HLSL, consultez [Comment : spécifier des propriétés de projet avec des pages de propriétés](../misc/how-to-specify-project-properties-with-property-pages.md).  
  
## Liste UIElement  
 **Nom de la variable dans l'en\-tête**  
 Spécifie le nom d'un tableau qui est code objet encodé utilisé de HLSL.  Le tableau est contenue dans un fichier d'en\-tête qui est sorti par le compilateur de HLSL.  Le nom du fichier d'en\-tête est spécifié par la propriété **Nom du fichier d'en\-tête** .  
  
 Cette propriété correspond à l'argument de ligne de commande des **\/Vn\[name\]** .  
  
 **Nom du fichier d'en\-tête**  
 Spécifie le nom du fichier d'en\-tête qui est sorti par le compilateur de HLSL.  L'en\-tête contient le code objet de HLSL qui est encodé dans un tableau.  Le nom du tableau est spécifié par la propriété **Nom de la variable dans l'en\-tête** .  
  
 Cette propriété correspond à l'argument de ligne de commande des **\/Fh\[name\]** .  
  
 **Nom de fichier objet**  
 Spécifie le nom du fichier objet qui est sorti par le compilateur de HLSL.  Par défaut, la valeur est **% $ \(OutDir\) \(nom de fichier\) .cso**.  
  
 Cette propriété correspond à l'argument de ligne de commande des **\/Fo\[name\]** .  
  
 **Sortie d'assembly**  
 **Liste réservé à l'assembly \(\/Fc\)** pour sortir uniquement des instructions en langage assembleur.  **Code d'assembly et hexa \(\/Fx\)** pour sortir les instructions en langage assembleur et l'op\- code correspondant au format hexadécimal.  Par défaut, aucun liste n'est sortie.  
  
 **Fichier de sortie d'assembly**  
 Spécifie le nom du fichier d'impression assembleur qui est sorti par le compilateur de HLSL.  
  
 Cette propriété correspond aux arguments de ligne de commande des **\/Fc\[name\]** et d' **\/Fx \[name\]** .  
  
## Voir aussi  
 [Pages de propriétés HLSL](../ide/hlsl-property-pages.md)   
 [Pages de propriétés HLSL : Général](../ide/hlsl-property-pages-general.md)   
 [Pages de propriétés HLSL : Avancé](../ide/hlsl-property-pages-advanced.md)