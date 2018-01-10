---
title: "Ajout d’un gestionnaire de messages ATL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4358dc54589971c559bec48adf77252d4f4cda28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-atl-message-handler"></a>Ajout d’un gestionnaire de messages ATL
Pour ajouter un gestionnaire de messages (une fonction membre qui gère les messages Windows) à un contrôle, sélectionnez tout d’abord le contrôle dans l’affichage de classes. Ouvrez le **propriétés** fenêtre, sélectionnez le **Messages** icône et cliquez sur la liste déroulante de contrôle dans la zone en regard du message requis. Cette opération ajoute une déclaration pour le Gestionnaire de messages dans le fichier d’en-tête du contrôle et une implémentation squelette du gestionnaire dans le fichier du contrôle .cpp. Il sera également ajouter la table des messages et ajoutez une entrée pour le gestionnaire.  
  
 Ajout d’un gestionnaire de messages dans ATL est similaire à l’ajout d’un gestionnaire de messages à une classe MFC. Consultez [Ajout d’un gestionnaire de messages MFC](../mfc/reference/adding-an-mfc-message-handler.md) pour plus d’informations.  
  
 Les conditions suivantes s’appliquent uniquement à l’ajout d’un gestionnaire de messages ATL :  
  
-   Les gestionnaires de messages suivent la même convention d’affectation de noms que MFC.  
  
-   Les nouvelles entrées de mappage de message sont ajoutées à la table des messages principale. L’Assistant ne reconnaît pas les tables des messages de remplacement et le chaînage des propriétés.  
  
## <a name="see-also"></a>Voir aussi  
 [Implémentation d’une fenêtre](../atl/implementing-a-window.md)

