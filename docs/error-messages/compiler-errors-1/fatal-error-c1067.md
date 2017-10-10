---
title: "Erreur irrécupérable C1067 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1067
dev_langs:
- C++
helpviewer_keywords:
- C1067
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7ef424de5d375f2d198a5f358976d058d556c506
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1067"></a>Erreur irrécupérable C1067
limite du compilateur : limite de 64 Ko sur la taille d’un enregistrement de type a été dépassé.  
  
 Cette erreur peut se produire si un symbole comporte un nom décoré dépassant 247 caractères.  Pour résoudre, raccourcissez le nom de symbole.  
  
 Lorsque le compilateur génère des informations de débogage, il émet des enregistrements de type pour définir les types rencontrés dans le code source.  Par exemple, les enregistrements de type incluent les structures simples et des listes d’arguments de fonctions.  Certains de ces enregistrements de type peuvent être longues listes.  
  
 Il existe une limite de 64 Ko de la taille de l’enregistrement de n’importe quel type.  Si cette limite de 64 Ko est dépassée. cette erreur se produit.  
  
 C1067 peut également se produire s’il existe de nombreux symboles avec des noms longs ou si une classe, struct ou union comporte trop de membres.
