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
ms.workload: cplusplus
ms.openlocfilehash: cb120103714c3711fb059fa736398458209b52a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0030"></a>Évaluateur d'expression, erreur CXX0030
expression non évaluée  
  
 Évaluateur d’expression du débogueur n’a pas pu obtenir une valeur pour l’expression lors de l’écriture. Une des causes possibles sont que l’expression fait référence à la mémoire qui est en dehors de l’espace d’adressage du programme (déréférencement d’un pointeur null est d’un exemple). Windows n’autorise pas l’accès à la mémoire qui est en dehors de l’espace d’adressage du programme.  
  
 Vous souhaiterez Réécrivez votre expression utilisant des parenthèses pour contrôler l’ordre d’évaluation.  
  
 Cette erreur est identique à CAN0030.