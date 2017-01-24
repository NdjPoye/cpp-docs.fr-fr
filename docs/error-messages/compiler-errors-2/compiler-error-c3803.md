---
title: "Erreur du compilateur C3803 | Microsoft Docs"
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
  - "C3803"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3803"
ms.assetid: bad5fb9a-ed9a-4c15-96e7-cf06e200a50d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3803
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'propriété' : la propriété possède un type incompatible avec l'un de ses accesseurs 'accesseur'  
  
 Le type d'une propriété défini avec [property](../../cpp/property-cpp.md) ne correspond pas au type de retour pour l'une de ses fonctions accesseur.  
  
 L'exemple suivant génère l'erreur C3803 :  
  
```  
// C3803.cpp  
struct A  
{  
   __declspec(property(get=GetIt)) int i;  
   char GetIt()  
   {  
      return 0;  
   }  
  
   /*  
   // try the following definition instead  
   int GetIt()  
   {  
      return 0;  
   }  
   */  
}; // C3803  
  
int main()  
{  
}  
```