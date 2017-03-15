---
title: "ComPtr::CopyTo, m&#233;thode | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::CopyTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CopyTo (méthode)"
ms.assetid: 8801bc49-6db4-4393-a55f-a701ae3b8718
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::CopyTo, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copie l'interface actuelle ou spécifiée associée à ce ComPtr vers le pointeur spécifié.  
  
## Syntaxe  
  
```  
HRESULT CopyTo(  
   _Deref_out_ InterfaceType** ptr  
);  
  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ void** ptr  
) const;  
template<  
   typename U  
>  
  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
) const;  
```  
  
#### Paramètres  
 `U`  
 Nom de type.  
  
 `ptr`  
 Lorsque cette opération se termine, un pointeur vers l'interface demandée.  
  
 `riid`  
 Un ID d'interface.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi ; sinon, un HRESULT indiquant pourquoi l'opération implicite de QueryInterface a échoué.  
  
## Remarques  
 La première fonction retourne une copie d'un pointeur vers l'interface associée à ce ComPtr.  Cette fonction retourne toujours S\_OK.  
  
 La deuxième fonction effectue une opération de QueryInterface sur l'interface associée à ce ComPtr pour l'interface spécifiée par le paramètre `riid`.  
  
 La troisième fonction effectue une opération de QueryInterface sur l'interface associée à ce ComPtr pour l'interface sous\-jacente du paramètre `U`.  
  
## Configuration requise  
 **En\-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)