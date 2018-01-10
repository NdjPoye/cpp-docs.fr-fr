---
title: "Sécurité de l’Automation à distance | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- AllowRemoteActivation [MFC]
- Remote Automation [MFC], security
- activating objects [MFC]
- security [MFC]
- Automation objects [MFC], security options
- object activation [MFC]
- security [MFC], Remote Automation
ms.assetid: 276b300d-c0b5-4bd8-8bf5-0270994b9cfa
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e535fac6330d6268629e8e3681fec47c7b0d65d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="security-in-remote-automation"></a>Sécurité dans l'automation à distance
Automation à distance prend en charge un niveau de base de sécurité pour permettre à un writer d’application serveur (ou son administrateur) spécifier la façon dont un objet spécifique peut être activé à distance. Tous les objets automation sur un système donné peuvent être globalement définis à « interdire l’activation à distance » ou « autoriser l’activation à distance ». En outre et plus souvent, des objets individuels peuvent être attribués à ces fonctionnalités. Automation à distance utilise une clé dans les paramètres du Registre de chaque objet, **AllowRemoteActivation**, afin de déterminer si un serveur donné peut être activé à distance. Si les paramètres du système utilisent ce mode, puis chaque objet dans le Registre peut être affecté à cette clé, et l’état individuelle de chacun d’eux peut être définie sur « Oui » ou « non » comme il convient.  
  
 Si le système du serveur est en cours d’exécution Windows NT ou Windows 2000, une autre forme de sécurité est autorisée. Dans ce cas, l’Automation à distance utilise la liste de contrôle d’accès (ACL) NT pour spécifier les utilisateurs ou les groupes d’utilisateurs peuvent activer à distance un serveur donné.  
  
 Notez que les options de sécurité s’appliquent à l’objet entier ; Il n’est pas possible de définir les attributs d’une interface spécifique, ou des propriétés individuelles ou des méthodes sur cet objet.  
  
 Toutes les options de sécurité peuvent être définies via le Gestionnaire de connexion d’Automation à distance (RAC).  
  
## <a name="see-also"></a>Voir aussi  
 [Automation à distance](../mfc/remote-automation.md)

