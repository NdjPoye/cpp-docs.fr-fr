---
title: Erreur du compilateur C2765 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2765
dev_langs: C++
helpviewer_keywords: C2765
ms.assetid: 47ad86f3-a7e0-47ad-85ff-0f5534458cb9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ec01af8ee743ff9eeccce11ed42c047149457ce6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2765"></a>Erreur du compilateur C2765
'fonction' : une spécialisation explicite d’un modèle de fonction ne peut pas avoir d’argument par défaut  
  
 Arguments par défaut ne sont pas autorisés sur une spécialisation explicite d’un modèle de fonction. Pour plus d’informations, consultez [spécialisation explicite des modèles de fonction](../../cpp/explicit-specialization-of-function-templates.md).  
  
 L’exemple suivant génère l’erreur C2765 :  
  
```  
// C2765.cpp  
template<class T> void f(T t) {};  
  
template<> void f<char>(char c = 'a') {}   // C2765  
// try the following line instead  
// template<> void f<char>(char c) {}  
```