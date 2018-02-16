---
title: "R6019 d’erreur d’exécution C | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6019
dev_langs:
- C++
helpviewer_keywords:
- R6019
ms.assetid: 8129923e-7db2-40ee-9602-def9365f8d28
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4ab7054bdce76aa1dd0b443993cfac8eeb8ecc7
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="c-runtime-error-r6019"></a>R6019 d’erreur d’exécution C
Impossible d’ouvrir le périphérique de la console  
  
> [!NOTE]
>  Si vous rencontrez ce message d’erreur lors de l’exécution d’une application, l’application a été arrêtée, car il a tenté d’accéder à la console, mais il ne dispose pas des autorisations suffisantes. Il existe plusieurs raisons possibles de cette erreur, mais il est généralement parce que le programme doit s’exécuter en tant qu’administrateur, ou il existe un bogue dans le programme.  
>   
>  Vous pouvez essayer de suivre les étapes ci-après pour corriger cette erreur :  
>   
>  -   Exécutez le programme en tant qu’administrateur.  
> -   Utilisez le **applications et fonctionnalités** ou **programmes et fonctionnalités** page dans le **le panneau de configuration** pour réparer ou réinstaller le programme.  
> -   Vérifiez **mise à jour Windows** dans les **le panneau de configuration** pour les mises à jour logicielles.  
> -   Recherchez une version mise à jour de l’application. Si le problème persiste, contactez le fournisseur de l’application.  
  
 **Informations pour les programmeurs**  
  
 Cette erreur se produit parce que l’application a appelé une fonction de la console, mais le système d’exploitation n’a pas accordé l’accès à la console. Sauf en mode débogage, fonctions de la console sont généralement pas autorisées dans les applications Microsoft Store. Si votre application nécessite des privilèges d’administrateur pour exécuter, vérifiez qu’il est installé pour s’exécuter en tant qu’administrateur par défaut.