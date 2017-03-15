---
title: "RaiseException, fonction | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::RaiseException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RaiseException (fonction)"
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RaiseException, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
inline void __declspec(noreturn)  
   RaiseException(  
      HRESULT hr,   
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);  
```  
  
#### Paramètres  
 `hr`  
 Le code de l'exception déclenchée; autrement dit, le HRESULT d'une opération ayant échoué.  
  
 `dwExceptionFlags`  
 Un indicateur spéifiant une exception signalable \(la valeur de l'indicateur est zéro\), ou une exception non signalable \(la valeur de l'indicateur est différente de zéro\).  Par défaut, l'exception est non signalable.  
  
## Remarques  
 Lève une exception dans le thread appelant.  
  
 Pour plus d'informations, consultez la fonction **RaiseException** de Windows.  
  
## Configuration requise  
 **En\-tête:** internal.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)