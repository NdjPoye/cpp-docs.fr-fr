---
title: "Erreur irrécupérable NMAKE U1099 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1099
dev_langs: C++
helpviewer_keywords: U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8bf8d662960e5857686f3f8301cc8481f350d4b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1099"></a>Erreur irrécupérable NMAKE U1099
dépassement de capacité de la pile  
  
 Le makefile en cours de traitement était trop complexe pour la taille de la pile dans NMAKE. NMAKE a une allocation de 0 x 3000 (12 Ko).  
  
 Pour augmenter l’allocation de pile de NMAKE, exécutez le [editbin /stack](../../build/reference/stack.md) utilitaire avec une option de pile plus importante :  
  
 **EDITBIN /STACK:reserve NMAKE. EXE**  
  
 où *réserver* est un nombre supérieur à l’allocation de pile en cours dans NMAKE.