---
title: "Erreur irr&#233;cup&#233;rable NMAKE U1045 | Microsoft Docs"
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
  - "U1045"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1045"
ms.assetid: dc70d162-14b9-4107-9237-7514044d72e3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable NMAKE U1045
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

échec de la génération dynamique : message  
  
 Un programme ou une commande appelé par NMAKE a échoué pour la raison indiquée.  Quand NMAKE appelle un autre programme \(par exemple, le compilateur ou l'éditeur de liens\), l'appel peut échouer ou une erreur peut être retournée par le programme appelé.  Ce message est utilisé pour signaler l'erreur.  
  
 Pour résoudre ce problème, commencez par déterminer la cause de l'erreur.  Vous pouvez utiliser les commandes indiquées par l'option [\/N](../../build/nmake-options.md) de NMAKE pour vérifier les paramètres d'environnement et répéter les actions effectuées par NMAKE sur la ligne de commande.