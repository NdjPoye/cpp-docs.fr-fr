---
title: "ComPtr::operator&amp;, op&#233;rateur | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::operator&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& (opérateur)"
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator&amp;, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Libère l'interface associée à cet objet `ComPtr` puis récupère l'adresse de l'objet `ComPtr` .  
  
## Syntaxe  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## Valeur de retour  
 Obtient une référence faible au `ComPtr` actuel.  
  
## Notes  
 Cette méthode diffère de [ComPtr::GetAddressOf](../windows/comptr-getaddressof-method.md) dans la mesure où cette méthode récupère une référence au pointeur d'interface.  Utilisez `ComPtr::GetAddressOf` lorsque vous avez besoin de l'adresse du pointeur d'interface mais ne souhaitez pas libérer cette interface.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)