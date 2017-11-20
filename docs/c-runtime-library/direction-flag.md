---
title: Balise de direction | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.flags
dev_langs: C++
helpviewer_keywords: direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b26cb08800bf7d2855c7972c63c0bea414d58c99
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="direction-flag"></a>Balise de direction
L’indicateur de direction est un indicateur de processeur spécifique pour les processeurs Intel 80x86. Il s’applique à toutes les instructions d’assembly qui utilisent le préfixe REP (répétition) REP, comme AVI, MOVSD, MOVSW et d’autres. Les adresses fournies aux instructions applicables sont augmentées si l’indicateur de direction est désactivé.  
  
 Les routines d’exécution C partent du principe que l’indicateur de direction est désactivé. Si vous utilisez d’autres fonctions avec les fonctions runtime C, vous devez vous assurer que les autres fonctions ne touchent pas à l’indicateur de direction ou qu’elles le restaurent à son état d’origine. Supposer que l’indicateur de direction est désactivé lors de l’entrée rend le code d’exécution plus rapide et plus efficace.  
  
 Les fonctions de bibliothèque Runtime C, comme les routines de manipulation de chaînes et de manipulation de la mémoire tampon s’attendent à ce que l’indicateur de direction soit désactivé.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctionnalités de bibliothèque CRT](../c-runtime-library/crt-library-features.md)