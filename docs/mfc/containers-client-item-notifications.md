---
title: "Conteneurs&#160;: notifications d&#39;&#233;l&#233;ment client | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "éléments clients et conteneurs OLE"
  - "notifications, conteneurs (élément client)"
  - "conteneurs OLE, élément client (notifications)"
ms.assetid: e1f1c427-01f5-45f2-b496-c5bce3d76340
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conteneurs&#160;: notifications d&#39;&#233;l&#233;ment client
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article traite des les fonctions substituables que l'infrastructure MFC appelle lorsque les applications du serveur modifient des éléments dans le document de votre application cliente.  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md) définit plusieurs fonctions substituables qui sont appelées en réponse aux requêtes de l'application du composant, également appelée l'application serveur.  Ces substituables agissent généralement comme des notifications.  Elles informent l'application conteneur des événements variés, tels que le défilement, l'activation, ou une modification de la position, et les modifications que l'utilisateur effectue en modifiant ou en manipulant l'élément.  
  
 L'infrastructure informe l'application des modifications via un appel à `COleClientItem::OnChange`, une fonction substituable dont l'implémentation est requise.  Cette fonction protégée accepte deux arguments.  La première instruction spécifie la raison pour laquelle le serveur a modifié l'élément:  
  
|Notification|Signification|  
|------------------|-------------------|  
|`OLE_CHANGED`|L'apparence de l'élément OLE a changé.|  
|`OLE_SAVED`|L'élément OLE a été enregistré.|  
|`OLE_CLOSED`|L'élément OLE a été fermé.|  
|**OLE Renommé**|Le document du serveur contenant l'élément OLE a été renommé.|  
|`OLE_CHANGED_STATE`|L'élément OLE est passé d'un état à un autre.|  
|**OLE\_CHANGED\_ASPECT**|L'aspect de l'élément OLE a été modifié par l'infrastructure.|  
  
 Ces valeurs sont de l'énumération de **OLE\_NOTIFICATION**, qui est définie dans AFXOLE.H.  
  
 Le deuxième argument pour la fonction spécifie la manière dont l'élément a changé ou l'état dans lequel il est passé.  
  
|Lorsque le premier argument est|Deuxième argument|  
|-------------------------------------|-----------------------|  
|`OLE_SAVED` ou `OLE_CLOSED`|n'est pas utilisé.|  
|`OLE_CHANGED`|Spécifie l'aspect d'élément OLE qui a changé.|  
|`OLE_CHANGED_STATE`|Décrit l'état de saisie \(`emptyState`, **loadedState**, `openState`, `activeState`, ou `activeUIState`\).|  
  
 Pour plus d'informations sur les états qu'un élément client peut assumer, consultez [Conteneurs : États d'éléments clients](../mfc/containers-client-item-states.md).  
  
 L'infrastructure appelle `COleClientItem::OnGetItemPosition` lorsqu'un élément est activé pour la modification sur place.  L'implémentation est requise pour les applications qui prennent en charge la modification sur place.  L'Application MFC fournit une implémentation de base, ce qui affecte les détails de l'élément à l'objet de `CRect` qui est transmis comme argument à `OnGetItemPosition`.  
  
 Si la position ou la taille d'un élément OLE change lors de la modification sur place, les informations du conteneur sur la position de l'élément et les rectangles de segment doivent être mis à jour et le serveur doit recevoir des informations concernant ces modifications.  L'infrastructure appelle `COleClientItem::OnChangeItemPosition` dans cet objectif.  L'Application MFC fournit une substitution qui appelle la fonction de la classe de base.  Vous devez modifier la fonction d'assistants Application générée pour votre `COleClientItem`\- classe dérivée afin que la fonction mette à jour toutes les informations regroupées par votre objet d'élément client.  
  
## Voir aussi  
 [Conteneurs](../mfc/containers.md)   
 [Conteneurs : états d'élément client](../mfc/containers-client-item-states.md)   
 [COleClientItem::OnChangeItemPosition](../Topic/COleClientItem::OnChangeItemPosition.md)