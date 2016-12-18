---
title: "D&#233;finitions et d&#233;clarations de fonctions | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "déclarer des fonctions"
  - "déclarer des fonctions, définitions de fonction"
  - "déclarations externes"
  - "liaison externe, déclarations de fonctions"
  - "définitions de fonction, déclarations de fonctions"
  - "prototypes de fonctions, éléments fondamentaux"
  - "déclarations internes"
  - "déclarations locales"
ms.assetid: 43fd98eb-7441-4473-a5d9-fc88c75577f7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;finitions et d&#233;clarations de fonctions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les prototypes de fonction établissent le nom de la fonction, son type de retour et le type et le nombre de ses paramètres formels.  Une définition de fonction comprend le corps de la fonction.  
  
## Remarques  
 Les déclarations de fonctions et de variables peuvent apparaître à l'intérieur ou à l'extérieur d'une définition de fonction.  Toute déclaration présente dans une définition de fonction est dite apparaître au niveau interne ou local.  Une déclaration extérieure à toutes les définitions de fonction est dite apparaître au niveau externe, global ou de la portée du fichier.  Les définitions variables, comme les déclarations, peuvent apparaître au niveau interne \(dans une définition de fonction\) ou au niveau externe \(à l'extérieur de toutes les définitions de fonction\).  Les définitions de fonction ont toujours lieu au niveau externe.  Les définitions de fonction sont décrites plus loin dans [Définitions de fonction](../c-language/c-function-definitions.md).  Les prototypes de fonction sont décrites dans [Prototypes de fonction](../c-language/function-prototypes.md).  
  
## Voir aussi  
 [Fichiers sources et programmes sources](../c-language/source-files-and-source-programs.md)