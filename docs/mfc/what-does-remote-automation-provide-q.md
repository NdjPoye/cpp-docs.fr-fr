---
title: "Que fournit l'automation à distance ? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Remote Automation, DCOM
ms.assetid: 269ad218-e164-40ef-9b87-25fcc8ba21de
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4a82b26a1e6c208a584dfd19ebfd4530b4bdf76
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="what-does-remote-automation-provide"></a>Que fournit l'automation à distance ?
Automation à distance permet aux programmes d’appeler `IDispatch` implémentations sur un ordinateur à partir d’un autre. Il prend également en charge les autres interfaces requises par Automation, en particulier **IEnumVARIANT** pour la prise en charge de la collection. Il ne fournit pas la possibilité de distribuer de toute autre interface COM (à l’exception de **IUnknown**, bien sûr) et, comme l’Automation normale, elle contient marshaling prise en charge uniquement pour les types de données pris en charge par Automation.  
  
 Cet ensemble de fonctionnalités permet à un programme accéder aux méthodes et propriétés, y compris celles qui retournent des collections ou autres objets automation, d’un objet en cours d’exécution sur un nœud réseau accessible. Si l’ordinateur client exécute également le logiciel approprié, il est possible pour le serveur rappeler le client, à l’aide des fonctionnalités d’Automation (cela fonctionne pour les clients 32 bits et 64 bits et est conceptuellement semblable aux événements, même si elle n’utilise pas le même mécanisme).  
  
 Pour une application fonctionne comme un serveur Automation à distance, il doit être implémenté en tant qu’exécutable (autrement dit, comme un « serveur local » plutôt que comme un « serveur inproc »).  
  
## <a name="see-also"></a>Voir aussi  
 [Quand l’Automation à distance se convient-elle](where-does-remote-automation-fit-in-q.md)   
 [Historique de DCOM](../mfc/history-of-dcom.md)
