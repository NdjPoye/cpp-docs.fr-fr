---
title: "Avertissement du compilateur (niveau 1) C4683 | Microsoft Docs"
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
  - "C4683"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4683"
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4683
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**'**   
 ***fonction* ' : la source d'événements a un paramètre de type 'out' ; faites attention lorsque vous raccordez plusieurs gestionnaires d'événements**  
  
 Si plusieurs récepteurs d'événements écoutent une source d'événement COM, la valeur d'un paramètre de sortie peut être ignorée.  
  
 Sachez qu'une fuite de mémoire peut se produire dans la situation suivante :  
  
1.  Si une méthode contient un paramètre de sortie affecté en interne, par exemple un BSTR \*.  
  
2.  Si l'événement contient plusieurs handlers \(autrement dit, s'il s'agit d'un événement multicast\).  
  
 La fuite s'explique par le fait que le paramètre de sortie doit être défini par plusieurs handlers, mais retourné sur le site d'appel par le dernier handler uniquement.  
  
 L'exemple suivant génère l'erreur C4683 :  
  
```  
// C4683.cpp  
// compile with: /W1 /LD  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[ module(name="xx") ];  
  
[ object ]  
__interface I {  
   HRESULT f([out] int* pi);  
   // try the following line instead  
   // HRESULT f(int* pi);  
};  
  
[ coclass, event_source(com) ]  
struct E {  
   __event __interface I;   // C4683  
};  
```