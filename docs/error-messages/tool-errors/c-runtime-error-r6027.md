---
title: "R6027 d’erreur d’exécution C | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6027
dev_langs:
- C++
helpviewer_keywords:
- R6027
ms.assetid: c06a62b3-08d9-4bf5-bcad-8340ec552f69
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
ms.openlocfilehash: 4aef25721268a90dca3358e96a52310a6caa0bb7
ms.lasthandoff: 02/24/2017

---
# <a name="c-runtime-error-r6027"></a>R6027 d’erreur d’exécution C
pas assez d’espace pour l’initialisation de lowio  
  
> [!NOTE]
>  Si vous rencontrez ce message d’erreur lors de l’exécution d’une application, l’application a été arrêtée car il a un problème de mémoire interne. Il existe plusieurs raisons possibles de cette erreur, mais il est généralement causé par une condition de mémoire. Il peut également être provoqué par un bogue dans l’application, par l’altération des bibliothèques Visual C++ qu’il utilise ou par un pilote.  
>   
>  Vous pouvez essayer de suivre les étapes ci-après pour corriger cette erreur :  
>   
>  -   Fermez les autres applications en cours d’exécution ou redémarrez votre ordinateur pour libérer de la mémoire.  
> -   Utilisez le **applications et fonctionnalités** ou **programmes et fonctionnalités** page dans le **le panneau de configuration** pour réparer ou réinstaller le programme.  
> -   Si l’application fonctionnait avant une installation récente d’une autre application ou le pilote, utilisez le **applications et fonctionnalités** ou **programmes et fonctionnalités** page dans le **le panneau de configuration** pour supprimer la nouvelle application ou le pilote et essayez à nouveau de votre application.  
> -   Utilisez le **applications et fonctionnalités** ou **programmes et fonctionnalités** page dans le **le panneau de configuration** pour réparer ou réinstaller toutes les copies de Microsoft Visual C++ Redistributable.  
> -   Vérifiez **mise à jour Windows** dans les **le panneau de configuration** pour les mises à jour logicielles.  
> -   Recherchez une version mise à jour de l’application. Si le problème persiste, contactez le fournisseur de l’application.  
  
 **Informations pour les programmeurs**  
  
 Cette erreur se produit lorsqu’il n’est pas suffisamment de mémoire disponible pour initialiser le support e/s de bas niveau dans le runtime C. Cette erreur se produit généralement lors du démarrage de l’application. Vérifiez que votre application et les DLL qu’il charge et les pilotes de ne pas endommager le segment de mémoire au démarrage.
