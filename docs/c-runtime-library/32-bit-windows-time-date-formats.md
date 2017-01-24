---
title: "Formats date/heure Windows 32&#160;bits | Microsoft Docs"
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
  - "vc.time"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Windows 32 bits"
ms.assetid: ef1589db-84d7-4b24-8799-7c7a22cfe2bf
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Formats date/heure Windows 32&#160;bits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'heure du fichier et la date sont stockées individuellement, en utilisant des entiers non signés comme des champs de bits.  L'heure du fichier et la date sont compressées comme suit :  
  
### Time  
  
|Position du bit :|0   1   2   3   4|5   6   7   8   9   A|B   C   D   E   F|  
|-----------------------|-----------------------|---------------------------|-----------------------|  
|length:|5|6|5|  
|Contenu :|heures|minutes|incréments de 2 seconde|  
|Champ de la valeur:|0–23|0–59|0\-29 dans des intervalles de 2 secondes|  
  
### Date  
  
|Position du bit :|0   1   2   3   4   5   6|7   8   9   A|B   C   D   E   F|  
|-----------------------|-------------------------------|-------------------|-----------------------|  
|length:|7|4|5|  
|Contenu :|year|month|Jour|  
|Champ de la valeur:|0–119|1–12|1–31|  
||\(par rapport à 1980\)|||  
  
## Voir aussi  
 [Constantes globales](../c-runtime-library/global-constants.md)