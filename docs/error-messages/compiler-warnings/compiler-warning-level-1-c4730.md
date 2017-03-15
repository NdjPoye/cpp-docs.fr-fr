---
title: "Avertissement du compilateur (niveau 1) C4730 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4730"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4730"
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4730
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'principal' : la combinaison de \_m64 et d'expressions en virgule flottante peut entraîner un code erroné  
  
 Une fonction utilise [\_\_m64](../../cpp/m64.md) et des types **float**\/**double**.  Du fait que les registres MMX et de virgule flottante partagent le même espace physique de registre \(ils ne peuvent pas être utilisés simultanément\), l'utilisation de `__m64` et des types **float**\/**double** dans la même fonction peut provoquer une altération des données et éventuellement donner lieu à une exception.  
  
 Pour pouvoir utiliser en toute sécurité les types `__m64` et virgule flottante dans la même fonction, chaque instruction qui emploie l'un de ces types doit être séparée intrinsèquement par **\_m\_empty\(\)** \(pour MMX\) ou **\_m\_femms\(\)** \(pour 3DNow\!\).  
  
 L'exemple suivant génère l'erreur C4730 :  
  
```  
// C4730.cpp  
// compile with: /W1  
// processor: x86  
#include "mmintrin.h"  
  
void func(double)  
{  
}  
  
int main(__m64 a, __m64 b)  
{  
   __m64 m;  
   double f;  
   f = 1.0;  
   m = _m_paddb(a, b);  
   // uncomment the next line to resolve C4730  
   // _m_empty();  
   func(f * 3.0);   // C4730  
}  
```