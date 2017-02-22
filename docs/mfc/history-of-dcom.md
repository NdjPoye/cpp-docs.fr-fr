---
title: "Historique de DCOM | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DCOM"
  - "DCOM, à propos de DCOM"
  - "Automation à distance, DCOM"
ms.assetid: c21aa0ea-1396-4b52-b77f-88fb0fdd2a5c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Historique de DCOM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque l'automation a été la première fois introduite début 1993, elle ne pouvait être utilisée qu'entre applications qui s'exécutaient sur le même ordinateur.  Toutefois, comme elle partageait les mêmes bases que le reste de OLE, c. \- à\-d., COM \(component object model\)\), il avait toujours été prévu qu'elle deviendrait « accessible à distance » lorsque COM lui\-même a été mis à jour pour inclure des fonctions de communication à distance.  Il était également prévu que la transition de l'opération purement locale à l'opération distribuée ne nécessite aucune ou peu d'édition du code existant.  
  
 Que signifie « à distance » ?  Le COM local stipulait que le consommateur d'une interface réside et s'exécute sur le même ordinateur que le fournisseur de cette interface.  Par exemple, Microsoft Visual Basic pouvait contrôler une copie de Microsoft Excel sur votre ordinateur de bureau, mais n'était pas capable de d'exécuter Excel sur un autre ordinateur.  Avec le développement COM distribué, le consommateur d'une interface n'a plus besoin de résider sur le même ordinateur que celui sur lequel le fournisseur d'interface s'exécute.  
  
 Une fois que COM fut approprié pour s'exécuter sur un réseau, alors toutes les interfaces qui n'étaient pas été liée à un modèle local d'exécution \(des interfaces se repose sur les fonctionnalités de l'ordinateur local, telles que ces interfaces de dessin dont méthodes ont des descripteurs des contextes de périphérique en tant que paramètres\) pouvaient être distribués.  Un consommateur d'interface faisait une demande d'une interface donnée ; cette interface pouvait être fournie par une instance d'un objet en cours d'exécution \(ou à exécuter\) sur un autre ordinateur.  Le mécanisme de distribution dans COM connectait le consommateur au fournisseur de sorte que les appels de méthode effectués par le consommateur apparaissaient du côté fournisseur, où ils étaient exécutés.  Toutes les valeurs de retour sont ensuite renvoyées au consommateur.  En pratique, la distribution est transparente pour le client et le fournisseur.  
  
 Des COM comme cela existent à présent.  DCOM \(pour « COM distribué »\) est livré avec les versions de Windows NT depuis la version 4,0 et notamment Windows 2000.  Depuis fin 1996, il a également été disponible pour Windows. 9x.  Dans les deux cas, DCOM comporte un jeu de remplacement et les DLL supplémentaires, avec quelques utilitaires, qui fournissent des fonctions locales et distantes COM.  Il s'agit donc désormais d'une partie inhérente des plateformes basées sur Win32, et sera disponible sur d'autres plateformes par d'autres organisations petit à petit.  
  
## Dans cette section  
 [Quand l'automation à distance convient\-elle ?](../mfc/where-does-remote-automation-fit-in-q.md)  
  
 [Que fournit l'automation à distance ?](../mfc/what-does-remote-automation-provide-q.md)  
  
## Voir aussi  
 [Automation à distance](../mfc/remote-automation.md)