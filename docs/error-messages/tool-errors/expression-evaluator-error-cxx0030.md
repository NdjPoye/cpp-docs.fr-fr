---
title: "Évaluateur d’expression, erreur CXX0030 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0030
dev_langs: C++
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ffa1dd85419943ede6a13d61cb82924c32b5e80a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0030"></a>Évaluateur d'expression, erreur CXX0030
expression non évaluée  
  
 Évaluateur d’expression du débogueur n’a pas pu obtenir une valeur pour l’expression lors de l’écriture. Une des causes possibles sont que l’expression fait référence à la mémoire qui est en dehors de l’espace d’adressage du programme (déréférencement d’un pointeur null est d’un exemple). Windows n’autorise pas l’accès à la mémoire qui est en dehors de l’espace d’adressage du programme.  
  
 Vous souhaiterez Réécrivez votre expression utilisant des parenthèses pour contrôler l’ordre d’évaluation.  
  
 Cette erreur est identique à CAN0030.