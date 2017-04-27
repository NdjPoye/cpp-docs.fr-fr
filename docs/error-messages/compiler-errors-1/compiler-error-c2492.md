---
title: Erreur du compilateur C2492 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2492
dev_langs:
- C++
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 54a650e967acb2ee0b6864780823111b4db9414c
ms.lasthandoff: 04/24/2017

---
# <a name="compiler-error-c2492"></a>Erreur du compilateur C2492
'*variable*' : les données avec une durée de stockage de thread ne peuvent pas avoir d’interface dll    
  
 La variable est déclarée avec le [thread](../../cpp/thread.md) d’attribut et avec la DLL de l’interface. L’adresse de le `thread` variable n’est pas connue jusqu'à moment de l’exécution, il ne peut pas être liée à une importation de DLL ou d’exportation.  
  
 L’exemple suivant génère C2492 :  
  
```  
// C2492.cpp  
// compile with: /c  
class C {  
public:  
   char   ch;  
};  
  
__declspec(dllexport) __declspec(thread) C c_1;   // C2492  
__declspec(thread) C c_1;   // OK  
```
