---
title: "Module::Create, m&#233;thode | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::Create"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Create (méthode)"
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::Create, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée une instance d’un module.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
WRL_NOTHROW static Module& Create();  
template<  
   typename T  
>  
WRL_NOTHROW static Module& Create(  
   T callback  
);  
template<  
   typename T  
>  
WRL_NOTHROW static Module& Create(  
   _In_ T* object,  
   _In_ void (T::* method)()  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type de module.  
  
 `callback`  
 Appelé lorsque le dernier objet d’instance du module est libéré.  
  
 `object`  
 Le `object` et `method` paramètres sont utilisés conjointement. Pointe vers le dernier objet d’instance lorsque le dernier objet d’instance dans le module est lancé.  
  
 `method`  
 Le `object` et `method` paramètres sont utilisés conjointement. Pointe vers la méthode du dernier objet instance lorsque le dernier objet d’instance dans le module est lancé.  
  
## <a name="return-value"></a>Valeur de retour  
 Référence au module.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
[Module (classe)](../windows/module-class.md)

 