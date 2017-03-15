---
title: "Erreur d’ex&#233;cution C R6025 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6025"
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur d&#39;ex&#233;cution C R6025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

appel de la fonction virtuelle pure  
  
 Aucun objet n'a été instancié pour gérer l'appel de la fonction virtuelle pure.  
  
 Si vous obtenez cette erreur dans une application, contactez le support technique responsable de votre application.  
  
 Cette erreur est due à un appel de fonction virtuelle dans une classe de base abstraite via un pointeur qui est créé par un cast vers le type de la classe dérivée, alors qu'il s'agit en fait d'un pointeur désignant la classe de base.  Cette situation se rencontre lors d'un cast de **void\*** vers un pointeur désignant une classe quand **void\*** a été créé pendant la construction de la classe de base.  
  
 Pour plus d'informations, consultez le site Web [Support de Microsoft](http://go.microsoft.com/fwlink/?LinkId=75220) .