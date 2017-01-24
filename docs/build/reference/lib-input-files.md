---
title: "Fichiers d&#39;entr&#233;e LIB | Microsoft Docs"
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
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers d'entrée, LIB"
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fichiers d&#39;entr&#233;e LIB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les fichiers d'entrée attendus par LIB dépendent du mode dans lequel celui\-ci est utilisé, comme le montre le tableau suivant.  
  
|Mode|Entrée|  
|----------|------------|  
|Par défaut \(génération ou modification d'une bibliothèque\)|Fichiers objets \(.obj\) COFF, bibliothèques \(.lib\) COFF, fichiers objets \(.obj\) OMF \(Object Model Format\) 32 bits|  
|Extraction d'un membre à l'aide de l'option \/EXTRACT|Bibliothèque \(.lib\) COFF|  
|Génération d'un fichier d'exportation et d'une bibliothèque d'importation à l'aide de l'option \/DEF|Fichier de définition \(.def\) de module, fichiers objets \(.obj\) COFF, bibliothèques \(.lib\) COFF, fichiers objets \(.obj\) OMF 32 bits|  
  
> [!NOTE]
>  Les bibliothèques OMF créées à l'aide de la version 16 bits de LIB ne peuvent pas être utilisées en tant qu'entrée dans la version 32 bits de LIB.  
  
## Voir aussi  
 [Vue d'ensemble de LIB](../../build/reference/overview-of-lib.md)