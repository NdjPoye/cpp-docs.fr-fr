---
title: "Évaluateur d’expression, erreur CXX0064 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0064
dev_langs: C++
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ada57d8df67054fa6577b128a6be73921fbb7e81
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0064"></a>Évaluateur d'expression, erreur CXX0064
ne peut pas définir le point d’arrêt sur fonction membre virtuelle liée  
  
 Un point d’arrêt a été définie sur une fonction membre virtuelle via un pointeur vers un objet, telle que :  
  
```  
pClass->vfunc( int );  
```  
  
 Un point d’arrêt peut être définie sur une fonction virtuelle en entrant la classe, par exemple :  
  
```  
Class::vfunc( int );  
```  
  
 Cette erreur est identique à CAN0064.