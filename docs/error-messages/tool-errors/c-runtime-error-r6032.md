---
title: "R6032 d’erreur d’exécution C | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6032
dev_langs: C++
helpviewer_keywords: R6032
ms.assetid: 52092a63-cc51-444a-bfc3-fad965a3558e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: afe6ba23315dfd00114e3d2b956a19cadf6342c3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6032"></a>R6032 d’erreur d’exécution C
Pas assez d’espace pour les informations de paramètres régionaux  
  
> [!NOTE]
>  Si vous rencontrez ce message d’erreur lors de l’exécution d’une application, l’application a été arrêtée, car il a un problème de mémoire interne. Il existe plusieurs raisons possibles de cette erreur, mais souvent, elle est provoquée par une condition de mémoire, ou par un bogue dans le programme.  
>   
>  Vous pouvez essayer de suivre les étapes ci-après pour corriger cette erreur :  
>   
>  -   Fermez les autres applications en cours d’exécution ou redémarrer votre ordinateur pour libérer la mémoire.  
> -   Utilisez le **applications et fonctionnalités** ou **programmes et fonctionnalités** page dans le **le panneau de configuration** pour réparer ou réinstaller le programme.  
> -   Vérifiez **mise à jour Windows** dans les **le panneau de configuration** pour les mises à jour logicielles.  
> -   Recherchez une version mise à jour de l’application. Si le problème persiste, contactez le fournisseur de l’application.  
  
 **Informations pour les programmeurs**  
  
 Le runtime gère les informations sur les paramètres régionaux sur chaque thread afin qu’il puisse traiter les appels aux fonctions sensibles aux paramètres régionaux. Si l’allocation de la mémoire pour ces informations échoue, le runtime ne peut pas poursuivre car un trop grand nombre de ses services de base en dépendent.