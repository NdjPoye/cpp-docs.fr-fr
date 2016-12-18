---
title: "EventSource::InvokeAll, m&#233;thode | Microsoft Docs"
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
  - "event/Microsoft::WRL::EventSource::InvokeAll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InvokeAll (méthode)"
ms.assetid: 1506618f-0421-4428-a4d0-4ea2b10a3bf6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# EventSource::InvokeAll, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Appelle chaque gestionnaire d’événements associé actuel [EventSource](../windows/eventsource-class.md) avec les types d’arguments spécifiés et les arguments de l’objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void InvokeAll();  
template <  
   typename T0  
>  
void InvokeAll(  
   T0arg0  
);  
template <  
   typename T0,  
   typename T1  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7,  
   typename T8  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7,  
   T8arg8  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7,  
   typename T8,  
   typename T9  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7,  
   T8arg8,  
   T9arg9  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T0`  
 Le type de l’argument de gestionnaire d’événements placée.  
  
 `T1`  
 Le type du premier argument de gestionnaire d’événements.  
  
 `T2`  
 Le type du second argument de gestionnaire d’événements.  
  
 `T3`  
 Le type du troisième argument de gestionnaire d’événements.  
  
 `T4`  
 Type du quatrième argument de gestionnaire d’événements.  
  
 `T5`  
 Type du cinquième argument de gestionnaire d’événements.  
  
 `T6`  
 Type du sixième argument de gestionnaire d’événements.  
  
 `T7`  
 Type du septième argument de gestionnaire d’événements.  
  
 `T8`  
 Type du huitième argument de gestionnaire événements.  
  
 `T9`  
 Type du neuvième argument de gestionnaire d’événements.  
  
 `arg0`  
 L’argument Gestionnaire d’événement placée.  
  
 `arg1`  
 Le premier argument de gestionnaire de l’événement.  
  
 `arg2`  
 Le deuxième argument de gestionnaire de l’événement.  
  
 `arg3`  
 Le troisième argument de gestionnaire de l’événement.  
  
 `arg4`  
 Quatrième argument de gestionnaire d’événements.  
  
 `arg5`  
 Le cinquième argument de gestionnaire de l’événement.  
  
 `arg6`  
 Sixième argument de gestionnaire d’événements.  
  
 `arg7`  
 Septième argument de gestionnaire d’événements.  
  
 `arg8`  
 L’argument Gestionnaire d’événement huitième.  
  
 `arg9`  
 Neuvième argument de gestionnaire d’événements.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** event.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [EventSource (classe)](../windows/eventsource-class.md)