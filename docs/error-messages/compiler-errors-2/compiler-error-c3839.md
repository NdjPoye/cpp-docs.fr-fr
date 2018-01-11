---
title: Erreur du compilateur C3839 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3839
dev_langs: C++
helpviewer_keywords: C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 36aa2146c142e66e61a8d1171cd4ba3acbb7bc96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3839"></a>Erreur du compilateur C3839
impossible de changer l'alignement dans un type managé ou WinRT  
  
 L’alignement des variables dans gérés ou les types Windows Runtime est contrôlé par le CLR ou Windows Runtime et ne peut pas être modifié avec [aligner](../../cpp/align-cpp.md).  
  
 L'exemple suivant génère l'erreur C3839 :  
  
```  
// C3839a.cpp  
// compile with: /clr  
ref class C  
{  
public:  
   __declspec(align(32)) int m_j; // C3839  
};  
  
int main()  
{  
}  
```