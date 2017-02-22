---
title: "Message Map Macros (ATL) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Message Map Macros (ATL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ces macros définissent des tables des messages et des entrées.  
  
|||  
|-|-|  
|[ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md)|Marque le début d'une table des messages secondaire.|  
|[BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)|Marque le début de la table des messages par défaut.|  
|[CHAIN\_MSG\_MAP\_ALT](../Topic/CHAIN_MSG_MAP_ALT.md)|Chaînes à une table des messages secondaire dans la classe de base.|  
|[CHAIN\_MSG\_MAP\_ALT\_MEMBER](../Topic/CHAIN_MSG_MAP_ALT_MEMBER.md)|Chaînes à une table des messages secondaire dans une donnée membre de la classe.|  
|[CHAIN\_MSG\_MAP](../Topic/CHAIN_MSG_MAP.md)|Chaînes dans la table des messages par défaut dans la classe de base.|  
|[CHAIN\_MSG\_MAP\_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md)|Chaînes dans la table des messages dans une autre classe au moment de l'exécution.|  
|[CHAIN\_MSG\_MAP\_MEMBER](../Topic/CHAIN_MSG_MAP_MEMBER.md)|Chaînes dans la table des messages par défaut dans une donnée membre de la classe.|  
|[COMMAND\_CODE\_HANDLER](../Topic/COMMAND_CODE_HANDLER.md)|Mappe un message de **WM\_COMMAND** à une fonction gestionnaire, selon le code de notification.|  
|[COMMAND\_HANDLER](../Topic/COMMAND_HANDLER.md)|Mappe un message de **WM\_COMMAND** à une fonction gestionnaire, selon le code de notification et l'identificateur de l'élément de menu, le contrôle, ou de l'accélérateur.|  
|[COMMAND\_ID\_HANDLER](../Topic/COMMAND_ID_HANDLER.md)|Mappe un message de **WM\_COMMAND** à une fonction gestionnaire, selon l'identificateur de l'élément de menu, le contrôle, ou de l'accélérateur.|  
|[COMMAND\_RANGE\_CODE\_HANDLER](../Topic/COMMAND_RANGE_CODE_HANDLER.md)|Mappe un message de **WM\_COMMAND** à une fonction gestionnaire, selon le code de notification et une plage contigu des identificateurs de contrôle.|  
|[COMMAND\_RANGE\_HANDLER](../Topic/COMMAND_RANGE_HANDLER.md)|Mappe un message de **WM\_COMMAND** à une fonction gestionnaire, en fonction d'une plage contigu des identificateurs de contrôle.|  
|[DECLARE\_EMPTY\_MSG\_MAP](../Topic/DECLARE_EMPTY_MSG_MAP.md)|Implémente une table des messages vide.|  
|[DEFAULT\_REFLECTION\_HANDLER](../Topic/DEFAULT_REFLECTION_HANDLER.md)|Fournit un gestionnaire par défaut pour les messages réfléchis qui ne sont pas gérés sinon.|  
|[END\_MSG\_MAP](../Topic/END_MSG_MAP.md)|Marque la fin d'une table des messages.|  
|[FORWARD\_NOTIFICATIONS](../Topic/FORWARD_NOTIFICATIONS.md)|Transféré à des messages de notification la fenêtre parente.|  
|[MESSAGE\_HANDLER](../Topic/MESSAGE_HANDLER.md)|Mappe une boîte de message windows à une fonction gestionnaire.|  
|[MESSAGE\_RANGE\_HANDLER](../Topic/MESSAGE_RANGE_HANDLER.md)|Mappe une plage contigu les messages windows à une fonction gestionnaire.|  
|[NOTIFY\_CODE\_HANDLER](../Topic/NOTIFY_CODE_HANDLER.md)|Mappe un message de **WM\_NOTIFY** à une fonction gestionnaire, selon le code de notification.|  
|[NOTIFY\_HANDLER](../Topic/NOTIFY_HANDLER.md)|Mappe un message de **WM\_NOTIFY** à une fonction gestionnaire, selon le code de notification et l'identificateur de contrôle.|  
|[NOTIFY\_ID\_HANDLER](../Topic/NOTIFY_ID_HANDLER.md)|Mappe un message de **WM\_NOTIFY** à une fonction gestionnaire, selon l'identificateur de contrôle.|  
|[NOTIFY\_RANGE\_CODE\_HANDLER](../Topic/NOTIFY_RANGE_CODE_HANDLER.md)|Mappe un message de **WM\_NOTIFY** à une fonction gestionnaire, selon le code de notification et une plage contigu des identificateurs de contrôle.|  
|[NOTIFY\_RANGE\_HANDLER](../Topic/NOTIFY_RANGE_HANDLER.md)|Mappe un message de **WM\_NOTIFY** à une fonction gestionnaire, en fonction d'une plage contigu des identificateurs de contrôle.|  
|[REFLECT\_NOTIFICATIONS](../Topic/REFLECT_NOTIFICATIONS.md)|Reflète les messages de notification dans la fenêtre qui les a envoyés.|  
|[REFLECTED\_COMMAND\_CODE\_HANDLER](../Topic/REFLECTED_COMMAND_CODE_HANDLER.md)|Mappe un message réfléchi de **WM\_COMMAND** à une fonction gestionnaire, selon le code de notification.|  
|[REFLECTED\_COMMAND\_HANDLER](../Topic/REFLECTED_COMMAND_HANDLER.md)|Mappe un message réfléchi de **WM\_COMMAND** à une fonction gestionnaire, selon le code de notification et l'identificateur de l'élément de menu, le contrôle, ou de l'accélérateur.|  
|[REFLECTED\_COMMAND\_ID\_HANDLER](../Topic/REFLECTED_COMMAND_ID_HANDLER.md)|Mappe un message réfléchi de **WM\_COMMAND** à une fonction gestionnaire, selon l'identificateur de l'élément de menu, le contrôle, ou de l'accélérateur.|  
|[REFLECTED\_COMMAND\_RANGE\_CODE\_HANDLER](../Topic/REFLECTED_COMMAND_RANGE_CODE_HANDLER.md)|Mappe un message réfléchi de **WM\_COMMAND** à une fonction gestionnaire, selon le code de notification et une plage contigu des identificateurs de contrôle.|  
|[REFLECTED\_COMMAND\_RANGE\_HANDLER](../Topic/REFLECTED_COMMAND_RANGE_HANDLER.md)|Mappe un message réfléchi de **WM\_COMMAND** à une fonction gestionnaire, en fonction d'une plage contigu des identificateurs de contrôle.|  
|[REFLECTED\_NOTIFY\_CODE\_HANDLER](../Topic/REFLECTED_NOTIFY_CODE_HANDLER.md)|Mappe un message réfléchi de **WM\_NOTIFY** à une fonction gestionnaire, selon le code de notification.|  
|[REFLECTED\_NOTIFY\_HANDLER](../Topic/REFLECTED_NOTIFY_HANDLER.md)|Mappe un message réfléchi de **WM\_NOTIFY** à une fonction gestionnaire, selon le code de notification et l'identificateur de contrôle.|  
|[REFLECTED\_NOTIFY\_ID\_HANDLER](../Topic/REFLECTED_NOTIFY_ID_HANDLER.md)|Mappe un message réfléchi de **WM\_NOTIFY** à une fonction gestionnaire, selon l'identificateur de contrôle.|  
|[REFLECTED\_NOTIFY\_RANGE\_CODE\_HANDLER](../Topic/REFLECTED_NOTIFY_RANGE_CODE_HANDLER.md)|Mappe un message réfléchi de **WM\_NOTIFY** à une fonction gestionnaire, selon le code de notification et une plage contigu des identificateurs de contrôle.|  
|[REFLECTED\_NOTIFY\_RANGE\_HANDLER](../Topic/REFLECTED_NOTIFY_RANGE_HANDLER.md)|Mappe un message réfléchi de **WM\_NOTIFY** à une fonction gestionnaire, en fonction d'une plage contigu des identificateurs de contrôle.|  
  
## Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)