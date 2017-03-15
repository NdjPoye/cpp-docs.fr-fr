---
title: "WeakReference::SetUnknown, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::WeakReference::SetUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetUnknown (méthode)"
ms.assetid: 5dddb9e3-a7c1-4195-8166-97c5ab6e972f
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# WeakReference::SetUnknown, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l’infrastructure/FAO et n’est pas destinée à être utilisée directement à partir de votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void SetUnknown(  
   _In_ IUnknown* unk  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `unk`  
 Un pointeur vers le `IUnknown` interface d’un objet.  
  
## <a name="remarks"></a>Notes  
 Définit la référence de l’utilisateur actuel forte `WeakReference` objet au pointeur d’interface spécifié.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** implements.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi
[WeakReference (classe)](../windows/weakreference-class1.md)  
 [Microsoft::wrl::Details Namespace](../windows/microsoft-wrl-details-namespace.md)