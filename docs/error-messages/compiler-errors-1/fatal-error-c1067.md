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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8889ccbfcac31917948da719444dab68a2d1b9c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1067"></a>Erreur irrécupérable C1067
limite du compilateur : limite de 64 Ko sur la taille d’un enregistrement de type a été dépassé.  
  
 Cette erreur peut se produire si un symbole comporte un nom décoré dépassant 247 caractères.  Pour résoudre, raccourcissez le nom de symbole.  
  
 Lorsque le compilateur génère des informations de débogage, il émet des enregistrements de type pour définir les types rencontrés dans le code source.  Par exemple, les enregistrements de type incluent les structures simples et des listes d’arguments de fonctions.  Certains de ces enregistrements de type peuvent être longues listes.  
  
 Il existe une limite de 64 Ko de la taille de l’enregistrement de n’importe quel type.  Si cette limite de 64 Ko est dépassée. cette erreur se produit.  
  
 C1067 peut également se produire s’il existe de nombreux symboles avec des noms longs ou si une classe, struct ou union comporte trop de membres.