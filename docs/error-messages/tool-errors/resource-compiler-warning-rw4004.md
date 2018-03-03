---
title: Avertissement RW4004 du compilateur de ressources | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RW4004
dev_langs:
- C++
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0249f7d01ee344f0fa17bdc39e58e9fce26c9b25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-warning-rw4004"></a>Avertissement RW4004 du compilateur de ressources 
Caractère ASCII non équivalent au code de touche virtuelle  
  
 Vous avez utilisé un littéral de chaîne pour le code de touche virtuelle dans un accélérateur de type VIRTKEY.  
  
 Cet avertissement ne vous empêche pas de continuer, mais sachez que les touches accélérateur générées risquent de ne pas correspondre à la chaîne spécifiée. (Les VIRTKEY utilisent des codes de touches différents des accélérateurs ASCII.)  
  
 Tandis que les littéraux de chaîne sont valides, vous assurer que vous obtenez l’accélérateur souhaité à l’aide de la **VK_\* #define** valeurs dans WINDOWS.h.