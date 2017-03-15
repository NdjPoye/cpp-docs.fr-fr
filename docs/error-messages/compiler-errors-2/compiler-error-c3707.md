---
title: "Erreur du compilateur C3707 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3707"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3707"
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3707
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : la méthode dispinterface doit avoir un dispid  
  
 Si vous utilisez une méthode `dispinterface`, vous devez lui assigner un `dispid`.  Pour remédier à cette erreur, assignez un `dispid` à la méthode `dispinterface`, par exemple en supprimant les marques de commentaire de l'attribut `id` sur la méthode dans l'exemple ci\-dessous.  Consultez les attributs [dispinterface](../../windows/dispinterface.md) et [id](../../windows/id.md) pour plus d'informations.  
  
 L'exemple suivant génère l'erreur C3707 :  
  
```  
// C3707.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(name="xx")];  
[dispinterface]  
__interface IEvents : IDispatch  
{  
   HRESULT event1([in] int i);   // C3707  
   // try the following line instead  
   // [id(1)] HRESULT event1([in] int i);  
};  
  
int main() {  
}  
```