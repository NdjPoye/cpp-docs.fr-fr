---
title: "À l’aide de IDispEventImpl (ATL) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f787fac05e95fff8a974692c3e6fca24561ed222
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-idispeventimpl"></a>À l’aide de IDispEventImpl
Lorsque vous utilisez `IDispEventImpl` pour gérer des événements, vous devez :  
  
-   Dérivez votre classe de [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
-   Ajoutez une table de récepteur d’événements à votre classe.  
  
-   Ajouter des entrées à la carte de récepteur événement à l’aide du [aide de SINK_ENTRY](reference/composite-control-macros.md#sink_entry) ou [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex) (macro).  
  
-   Implémentez les méthodes que vous êtes intéressé par la gestion.  
  
-   Conseille et déconseiller la source d’événements.  
  
## <a name="example"></a>Exemple  
 L’exemple ci-dessous montre comment gérer les **DocumentChange** événements déclenchement par de Word **Application** objet. Cet événement est défini en tant que méthode sur le **ApplicationEvents** dispinterface.  
  
 L’exemple est issu le [exemple ATLEventHandling](../visual-cpp-samples.md).  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 L’exemple utilise `#import` pour générer les fichiers d’en-tête requis à partir de la bibliothèque de types de Word. Si vous souhaitez utiliser cet exemple avec d’autres versions de Word, vous devez spécifier le fichier dll mso approprié. Par exemple, Office 2000 fournit mso9.dll et OfficeXP fournit mso.dll. Ce code est simplifié de stdafx.h :  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]  
  
 Le code suivant s’affiche dans NotSoSimple.h. Le code est indiqué par des commentaires :  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion des événements](../atl/event-handling-and-atl.md)   
 [ATLEventHandling, exemple](../visual-cpp-samples.md)

