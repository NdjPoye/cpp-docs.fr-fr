---
title: "Implémenter l’Assistant Point de connexion | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.impl.cp.overview
dev_langs: C++
helpviewer_keywords: Implement Connection Point Wizard [C++]
ms.assetid: c117f6c6-30f0-4adb-82b4-b1f34e0f0fa8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a7efade7f0bd0a3c35e02439818873b923c1ac1d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="implement-connection-point-wizard"></a>Assistant Implémentation d'un point de connexion
Cet Assistant implémente un point de connexion pour un objet COM. Un objet connectable (c'est-à-dire une source) peut exposer un point de connexion pour ses propres interfaces ou pour toute interface sortante. Visual C++ et Windows fournissent tous deux bibliothèques de types qui ont des interfaces sortantes. Chaque interface sortante peut être implémentée par un client sur un objet (autrement dit, un récepteur).  
  
 Pour plus d’informations, consultez [Points de connexion ATL](../atl/atl-connection-points.md).  
  
 **Bibliothèques de types disponibles**  
 Affiche les bibliothèques de types disponibles contenant les définitions d’interface pour laquelle vous pouvez implémenter des points de connexion. Cliquez sur le bouton de sélection pour rechercher un fichier contenant la bibliothèque de types à utiliser.  
  
 **Emplacement**  
 Affiche l’emplacement de la bibliothèque de types actuellement sélectionnée dans le **bibliothèques de types disponibles** liste.  
  
 **Interfaces**  
 Affiche les interfaces dont les définitions sont contenues dans la bibliothèque de types actuellement sélectionnée dans le **bibliothèques de types disponibles** boîte.  
  
|Bouton de transfert|Description|  
|---------------------|-----------------|  
|**>**|Ajoute à la **implémenter les points de connexion** liste le nom d’interface actuellement sélectionné dans le **Interfaces** liste.|  
|**>>**|Ajoute à la **implémenter les points de connexion** répertorier tous les noms d’interface disponibles dans le **Interfaces** liste.|  
|**<**|Supprime le nom d’interface actuellement sélectionné dans le **implémenter les points de connexion** liste.|  
|**<<**|Supprime tous les noms de l’interface du **implémenter les points de connexion** liste.|  
  
 **Implémenter les points de connexion**  
 Affiche les noms des interfaces pour lesquelles vous implémentez des points de connexion lorsque vous cliquez sur **Terminer**.  
  
## <a name="see-also"></a>Voir aussi  
 [Implémentation d’un Point de connexion](../ide/implementing-a-connection-point-visual-cpp.md)