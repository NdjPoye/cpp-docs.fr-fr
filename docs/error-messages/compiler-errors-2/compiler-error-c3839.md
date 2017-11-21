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
ms.openlocfilehash: 8a8c9fa9112128b86123693aea7443d68e8531d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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