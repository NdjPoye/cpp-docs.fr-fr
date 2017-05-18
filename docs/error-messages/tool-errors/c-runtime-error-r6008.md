---
title: "R6008 d’erreur d’exécution C | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6008
dev_langs:
- C++
helpviewer_keywords:
- R6008
ms.assetid: f0f304fc-709a-4843-bc7e-bad1ae0d1649
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7ff8749859bd9f0300a606c7cc5e328873fe1f5c
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="c-runtime-error-r6008"></a>R6008 d’erreur d’exécution C
espace insuffisant pour les arguments  
  
> [!NOTE]
>  Si vous rencontrez ce message d’erreur lors de l’exécution d’une application, l’application a été arrêtée car il a un problème de mémoire interne. Il existe plusieurs raisons possibles de cette erreur, mais souvent, elle est provoquée par une condition de mémoire faible, trop de mémoire occupée par les variables d’environnement ou un bogue dans le programme.  
>   
>  Vous pouvez essayer de suivre les étapes ci-après pour corriger cette erreur :  
>   
>  -   Fermez les autres applications en cours d’exécution ou redémarrez votre ordinateur pour libérer de la mémoire.  
> -   Réduire le nombre et la taille des arguments de ligne de commande à l’application.  
> -   Utilisez le **applications et fonctionnalités** ou **programmes et fonctionnalités** page dans le **le panneau de configuration** pour réparer ou réinstaller le programme.  
> -   Vérifiez **mise à jour Windows** dans les **le panneau de configuration** pour les mises à jour logicielles.  
> -   Recherchez une version mise à jour de l’application. Si le problème persiste, contactez le fournisseur de l’application.  
  
 **Informations pour les programmeurs**  
  
 Il a été suffisamment de mémoire pour charger le programme mais suffisante pour créer le **argv** tableau. Cela peut être dû en conditions de mémoire ou en exceptionnellement élevé de lignes de commande ou l’utilisation de variables d’environnement. Considérez l’une des solutions suivantes :  
  
-   Augmentez la quantité de mémoire disponible pour le programme.  
  
-   Réduire le nombre et la taille des arguments de ligne de commande.  
  
-   Réduire la taille de l’environnement en supprimant les variables superflues.
