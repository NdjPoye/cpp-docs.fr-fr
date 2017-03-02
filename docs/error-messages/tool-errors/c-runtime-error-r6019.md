---
title: "R6019 d’erreur d’exécution C | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6019
dev_langs:
- C++
helpviewer_keywords:
- R6019
ms.assetid: 8129923e-7db2-40ee-9602-def9365f8d28
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 0a490fa1c15c3c2dc3285af6c69689c2a7fbd4b6
ms.lasthandoff: 02/24/2017

---
# <a name="c-runtime-error-r6019"></a>R6019 d’erreur d’exécution C
Impossible d’ouvrir le périphérique de console  
  
> [!NOTE]
>  Si vous rencontrez ce message d’erreur lors de l’exécution d’une application, l’application a été arrêtée car il a tenté d’accéder à la console, mais il ne disposait pas des autorisations suffisantes. Il existe plusieurs raisons possibles de cette erreur, mais il est généralement parce que le programme doit être exécuté en tant qu’administrateur, ou il existe un bogue dans le programme.  
>   
>  Vous pouvez essayer de suivre les étapes ci-après pour corriger cette erreur :  
>   
>  -   Exécutez le programme en tant qu’administrateur.  
> -   Utilisez le **applications et fonctionnalités** ou **programmes et fonctionnalités** page dans le **le panneau de configuration** pour réparer ou réinstaller le programme.  
> -   Vérifiez **mise à jour Windows** dans les **le panneau de configuration** pour les mises à jour logicielles.  
> -   Recherchez une version mise à jour de l’application. Si le problème persiste, contactez le fournisseur de l’application.  
  
 **Informations pour les programmeurs**  
  
 Cette erreur se produit parce que l’application a appelé une fonction de la console, mais le système d’exploitation n’a pas accordé l’accès à la console. Sauf en mode débogage, fonctions de la console sont généralement pas autorisées dans les applications du Windows Store. Si votre application requiert des privilèges d’administrateur pour exécuter, vérifiez qu’il est installé pour s’exécuter en tant qu’administrateur par défaut.
