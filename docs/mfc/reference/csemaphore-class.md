---
title: "CSemaphore Class | Microsoft Docs"
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
  - "CSemaphore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSemaphore class"
  - "sémaphores"
  - "synchronization objects, sémaphores"
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSemaphore Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un objet de classe `CSemaphore` représentant une « sémaphore » — un objet de synchronisation qui permet à un nombre limité de threads dans un ou plusieurs processus pour accéder à un met à jour le nombre de threads qui accèdent simultanément en cours à une ressource spécifiée.  
  
## Syntaxe  
  
```  
class CSemaphore : public CSyncObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSemaphore::CSemaphore](../Topic/CSemaphore::CSemaphore.md)|Construit un objet `CSemaphore`.|  
  
## Notes  
 Les sémaphores sont utiles dans le contrôle de l'accès à une ressource partagée qui peut prendre en charge un nombre limité d'utilisateurs.  Nombre actuel de l'objet d' `CSemaphore` est le nombre d'utilisateurs sont autorisés.  Lorsque le compteur atteint zéro, toute tentative d'utiliser la ressource contrôlée par l'objet de **CSemaphore** sont insérées dans une file d'attente système et attente jusqu'à ce que elles ou chronomètrent ou le nombre monte au\-dessus de 0.  Le nombre maximal d'utilisateurs qui peuvent accéder à la ressource contrôlée en même temps est spécifié pendant la construction de l'objet d' `CSemaphore` .  
  
 Pour utiliser un objet de **CSemaphore** , construisez l'objet d' `CSemaphore` aisément.  Spécifiez le nom de le sémaphore que vous souhaitez à l'attente sur, et que votre application doit initialement la propriétaire.  Vous pouvez ensuite accéder à un sémaphore lorsque le constructeur retourne.  Appelez [CSyncObject::Unlock](../Topic/CSyncObject::Unlock.md) lorsque vous avez terminé de l'accès à la ressource contrôlée.  
  
 Une autre méthode pour l'utilisation des objets d' `CSemaphore` consiste à ajouter une variable de type `CSemaphore` comme une donnée membre à la classe que vous souhaitez au contrôle.  Pendant la construction de l'objet contrôlé, appelez le constructeur de la donnée membre d' `CSemaphore` spécifiant le nombre initial d'accès, le nombre maximal d'accès, le nom de le sémaphore \(si elle est utilisée au delà de les limites de processus\), les attributs de sécurité souhaités.  
  
 Pour accéder aux ressources contrôlées par les objets d' `CSemaphore` de cette manière, commencez par créer une variable de type [CSingleLock](../../mfc/reference/csinglelock-class.md) ou tapez [CMultiLock](../../mfc/reference/cmultilock-class.md) dans la fonction membre de l'accès à la ressource.  Appelez la fonction membre d' `Lock` de l'objet lock \(par exemple, [CSingleLock::Lock](../Topic/CSingleLock::Lock.md)\).  À ce stade, votre thread accédera à la ressource attente, la ressource à libérer et accédera, ou attend la ressource à libérer et la chronomètrera, ne pas accéder à la ressource.  Dans tous les cas, la ressource a été accessible en mode thread\-safe.  Pour libérer les ressources, utilisez la fonction membre d' `Unlock` de l'objet lock \(par exemple, [CSingleLock::Unlock](../Topic/CSingleLock::Unlock.md)\), ou autorisez l'objet lock à la partie hors de portée.  
  
 Sinon, vous pouvez créer un objet de **CSemaphore** autonome, et y accéder explicitement avant d'essayer d'accéder à la ressource contrôlée.  Cette méthode, tandis que clearer à un utilisateur qui lit votre code source, est une erreur plus encline.  
  
 Pour plus d'informations sur l'utilisation des objets de **CSemaphore** , consultez l'article [Multithreading : Comment utiliser les classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CSemaphore`  
  
## Configuration requise  
 **Header:** afxmt.h  
  
## Voir aussi  
 [CSyncObject Class](../../mfc/reference/csyncobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)