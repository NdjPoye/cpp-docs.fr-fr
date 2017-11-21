---
title: "L’utilisation de la pile | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c7a74abff7a2971fe66fa2df878078ac95f58fe8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="stack-usage"></a>Utilisation de la pile
Toute la mémoire au-delà de l’adresse actuelle de RSP est considérée comme volatile : le système d’exploitation ou un débogueur, peut remplacer cette mémoire pendant une session de débogage d’utilisateur ou un gestionnaire d’interruption. Par conséquent, RSP doit toujours être défini avant de tenter de lire ou écrire des valeurs dans un frame de pile.  
  
 Cette section décrit l’allocation d’espace de pile pour les variables locales et les **alloca** intrinsèque.  
  
-   [Allocation de piles](../build/stack-allocation.md)  
  
-   [Construction dynamique d’une zone pour la pile de paramètres](../build/dynamic-parameter-stack-area-construction.md)  
  
-   [Types de fonctions](../build/function-types.md)  
  
-   [Alignement avec malloc](../build/malloc-alignment.md)  
  
-   [alloca](../build/alloca.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Conventions des logiciels x64](../build/x64-software-conventions.md)