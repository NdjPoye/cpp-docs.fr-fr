---
title: Erreur du compilateur C3398 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3398
dev_langs:
- C++
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 66bd229369456da18d8bed60b25b6e6b07e03f27
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3398"></a>Erreur du compilateur C3398
'operator' : impossible de convertir de 'function_signature' en 'function_pointer'. L'expression source doit être un symbole de fonction  
  
 Lorsque le [__clrcall](../../cpp/clrcall.md) convention d’appel n’est pas spécifié lors de la compilation avec **/CLR**, le compilateur génère deux points d’entrée (adresses) pour chaque fonction, un point d’entrée natif et un point d’entrée managé.  
  
 Par défaut, le compilateur retourne le point d’entrée natif, mais dans certains cas, il est souhaitable d’avoir un point d’entrée managé (par exemple, lors de l’assignation de l’adresse à un pointeur de fonction `__clrcall` ). Pour que le compilateur puisse choisir de manière fiable le point d’entrée managé dans une assignation, le côté droit doit être un symbole de fonction.
