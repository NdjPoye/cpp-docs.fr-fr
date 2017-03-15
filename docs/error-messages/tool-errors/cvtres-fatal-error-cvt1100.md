---
title: "Erreur irr&#233;cup&#233;rable CVTRES CVT1100 | Microsoft Docs"
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
  - "CVT1100"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CVT1100"
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable CVTRES CVT1100
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ressource dupliquée. type:type, name:nom, language:langage, flags:indicateurs, size:taille  
  
 La ressource donnée a été spécifiée plusieurs fois.  
  
 Vous pouvez obtenir cette erreur si l'éditeur de liens crée une bibliothèque de types alors que vous n'avez pas spécifié [\/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) et qu'une ressource de votre projet utilise déjà 1.  Dans ce cas, spécifiez \/TLBID et indiquez un autre nombre inférieur ou égal à 65 535.