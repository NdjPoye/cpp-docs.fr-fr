---
title: Erreur du compilateur C2708 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2708
dev_langs: C++
helpviewer_keywords: C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8ce9eb29c776c7d98a7fbad4dc95959180045256
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2708"></a>Erreur du compilateur C2708
'identificateur' : longueur en octets des paramètres réels diffère d’appel précédent ou référence  
  
 A [__stdcall](../../cpp/stdcall.md) fonction doit être précédée d’un prototype. Sinon, le compilateur interprète le premier appel à la fonction en tant que prototype et cette erreur se produit lorsque le compilateur rencontre un appel qui ne correspond pas.  
  
 Pour résoudre ce problème, ajoutez un prototype de fonction.