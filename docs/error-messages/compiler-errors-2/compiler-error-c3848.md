---
title: Erreur du compilateur C3848 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3848
dev_langs:
- C++
helpviewer_keywords:
- C3848
ms.assetid: 32d3ccef-01ec-4f8b-bbff-fb9b1a76b4c4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3420a5baa2bfca8a19271ccb3f3c3dc64e6fd12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3848"></a>Erreur du compilateur C3848
expression ayant le type 'type' perdrait certains qualificateurs const-volatile afin d’appeler 'fonction'  
  
 Une variable avec un type const-volatile peut uniquement appeler des membres fonctions avec des qualifications const-volatile égales ou supérieures.  
  
 Les exemples suivants génèrent C3848 :  
  
```  
// C3848.cpp  
void glbFunc1()  
{  
}  
  
typedef void (* pFunc1)();  
  
struct S3  
{  
   operator pFunc1() // const  
   {  
      return &glbFunc1;  
   }  
};  
  
int main()  
{  
   const S3 s3;  
   s3();   // C3848, uncomment const qualifier  
}  
```