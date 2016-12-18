---
title: "Blocks | Microsoft Docs"
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
  - "blocs"
  - "instructions composées"
  - "définitions de fonction, blocs dans code"
  - "instructions, composée"
ms.assetid: be231a92-c712-464e-ae25-a4becb20f7f5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Blocks
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une séquence de déclarations, de définitions et d'instructions placées entre accolades \(**{ }**\) est appelée un « bloc ». Il existe deux types de bloc en C.  L'« instruction composée, » une instruction composée d'une ou plusieurs instructions \(consultez [L'instruction composée](../c-language/compound-statement-c.md)\), est un type de bloc.  L'autre, la « définition de fonction », se compose d'une instruction composée \(le corps de la fonction\) et de l'« en\-tête » associé de la fonction \(le nom de la fonction, le type de retour et les paramètres formels\).  Un bloc au sein d'autres blocs est dit « imbriqué ».  
  
 Toutes les instructions composées sont placées entre accolades. En revanche, tous les éléments délimités par des accolades ne constituent pas une instruction composée.  Par exemple, bien que les spécifications des éléments de tableau, de structure ou d'énumération puissent apparaître entre accolades, ce ne sont pas des instructions composées.  
  
## Voir aussi  
 [Fichiers sources et programmes sources](../c-language/source-files-and-source-programs.md)