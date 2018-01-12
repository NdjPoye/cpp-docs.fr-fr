---
title: Erreur du compilateur C2492 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2492
dev_langs: C++
helpviewer_keywords: C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5410af24b5300b2c03aa0ed4e121abceb6d6d483
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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