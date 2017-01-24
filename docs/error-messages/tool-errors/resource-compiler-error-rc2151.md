---
title: "Erreur RC2151 du compilateur de ressources  | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC2151"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2151"
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur RC2151 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de réutiliser les constantes de chaînes  
  
 Vous avez utilisé deux fois la même valeur dans une instruction **STRINGTABLE**.  Évitez d'utiliser des valeurs décimales et hexadécimales qui se chevauchent.  
  
 Chaque ID d'une instruction **STRINGTABLE** doit être unique.  Pour un résultat optimal, utilisez des constantes contiguës commençant par un multiple de 16.