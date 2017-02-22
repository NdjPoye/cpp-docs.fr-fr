---
title: "D&#233;veloppement de votre propre fonction d&#39;assistance | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonctions d'assistance"
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# D&#233;veloppement de votre propre fonction d&#39;assistance
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez choisir de fournir votre propre version de la routine pour exécuter un traitement spécifique en fonction des noms des DLL ou des importations.  Pour cela, vous disposez de deux méthodes : soit le codage de votre propre fonction, éventuellement sur la base du code fourni, soit le raccordement de la version fournie à l'aide des raccordements de notification déjà décrits par ailleurs.  
  
 Codage de votre propre fonction  
 Cette méthode est assez simple, puisqu'il s'agit en fait d'utiliser comme modèle le code fourni.  Le nouveau code doit bien sûr respecter les conventions d'appel et, s'il fait référence aux thunks générés par l'éditeur de liens, il doit retourner un pointeur fonction correct.  Dès lors que vous êtes dans votre code, vous pouvez faire à peu près tout ce que vous souhaitez pour répondre à l'appel ou en sortir.  
  
 Utilisation du raccordement de notification de démarrage du traitement  
 Il est probablement plus facile de vous contenter de fournir un nouveau pointeur à une fonction de raccordement de notification fournie par l'utilisateur qui reçoit les mêmes valeurs que l'assistance par défaut lors de la notification dliStartProcessing.  À ce stade, la fonction de raccordement peut devenir la nouvelle fonction d'assistance, étant donné qu'un retour réussi à l'assistance par défaut va ignorer tout traitement supplémentaire dans l'assistance par défaut.  
  
## Voir aussi  
 [Prise en charge de l'éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)