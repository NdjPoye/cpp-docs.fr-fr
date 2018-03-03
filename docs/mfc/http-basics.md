---
title: Principes de base HTTP | Documents Microsoft
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
- HTTP [MFC], return codes
- return codes [MFC]
- HTTP requests [MFC], return codes
ms.assetid: 5b7421bf-42c8-4f3a-8566-8ff5957f58cc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 67921e0667267b99b3787d55fa7ff564aa543ae7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="http-basics"></a>Éléments fondamentaux relatifs à HTTP
Lorsque vous écrivez une application internet, vous examinez et ajoutez aux informations d’en-tête HTTP. Codes de retour indiquent la réussite ou l’échec de l’événement demandé. Plusieurs codes de retour courants sont répertoriés dans le tableau suivant.  
  
|Code de retour|Signification|  
|-----------------|-------------|  
|200|L’URL est localisée, la transmission suit.|  
|400|Demande inintelligible|  
|404|Demande d’URL introuvable|  
|405|Serveur ne prend pas en charge la méthode demandée|  
|500|Erreur de serveur inconnue|  
|503|Service non disponible|  
  
 Les réponses HTTP sont regroupées comme indiqué dans le tableau suivant.  
  
|Regrouper|Signification|  
|-----------|-------------|  
|200-299|Opération réussie|  
|300-399|Information|  
|400-499|Erreur de requête|  
|500-599|Erreur de serveur|  
  
 Le protocole HTTP (Hypertext Transfer) est un protocole de niveau application pour les systèmes d’information hypermédias. Pour plus d’informations sur HTTP et la manière dont les serveurs et les navigateurs Web communiquent, consultez la spécification de protocole HTTP (Hypertext Transfer) :  
  
 [http://www.w3.org/pub/www/Protocols/](http://www.w3.org/pub/www/protocols/)  
  
## <a name="see-also"></a>Voir aussi  
 [Notions de base de la programmation Internet MFC](../mfc/mfc-internet-programming-basics.md)

