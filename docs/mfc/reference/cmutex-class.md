---
title: "CMutex Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "Mutex"
  - "CMutex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMutex class"
  - "mutex"
  - "classes de synchronisation, CMutex class"
  - "synchronization objects, mutex"
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMutex Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente un « mutex » — un objet de synchronisation qui permet à un thread mutuellement accès exclusif à une ressource.  
  
## Syntaxe  
  
```  
class CMutex : public CSyncObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMutex::CMutex](../Topic/CMutex::CMutex.md)|Construit un objet `CMutex`.|  
  
## Notes  
 Mutex est utile lorsqu'il peut permettre à un seul thread à la fois pour modifier les données ou une autre ressource contrôlée.  Par exemple, ajouter des nœuds à une liste liée est un processus qui doit être autorisé par un seul thread à la fois.  À l'aide d'un objet d' `CMutex` pour contrôler la liste liée, un seul thread à la fois peut accéder à la liste.  
  
 Pour utiliser un objet d' `CMutex` , construisez l'objet d' `CMutex` aisément.  Spécifiez le nom des mutex que vous souhaitez à l'attente sur, et que votre application doit initialement la propriétaire.  Vous pouvez ensuite accéder aux mutex lorsque le constructeur retourne.  Appelez [CSyncObject::Unlock](../Topic/CSyncObject::Unlock.md) lorsque vous avez terminé de l'accès à la ressource contrôlée.  
  
 Une autre méthode pour l'utilisation des objets d' `CMutex` consiste à ajouter une variable de type `CMutex` comme une donnée membre à la classe que vous souhaitez au contrôle.  Pendant la construction de l'objet contrôlé, appelez le constructeur de spécifier des données membre d' `CMutex` si le mutex est initialement possédé, le nom des mutex \(s'il est utilisé au delà de les limites de processus\), et d'attributs de sécurité souhaités.  
  
 Pour accéder aux ressources contrôlées par les objets d' `CMutex` de cette manière, commencez par créer une variable de type [CSingleLock](../../mfc/reference/csinglelock-class.md) ou tapez [CMultiLock](../../mfc/reference/cmultilock-class.md) dans la fonction membre de l'accès à la ressource.  Appelez la fonction membre d' `Lock` de l'objet lock \(par exemple, [CSingleLock::Lock](../Topic/CSingleLock::Lock.md)\).  À ce stade, votre thread accédera à la ressource attente, la ressource à libérer et accédera, ou attend la ressource à libérer et la chronomètrera, ne pas accéder à la ressource.  Dans tous les cas, la ressource a été accessible en mode thread\-safe.  Pour libérer les ressources, utilisez la fonction membre d' `Unlock` de l'objet lock \(par exemple, [CSingleLock::Unlock](../Topic/CSingleLock::Unlock.md)\), ou autorisez l'objet lock à la partie hors de portée.  
  
 Pour plus d'informations sur l'utilisation des objets d' `CMutex` , consultez l'article [Multithreading : Comment utiliser les classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CMutex`  
  
## Configuration requise  
 **Header:** afxmt.h  
  
## Voir aussi  
 [CSyncObject Class](../../mfc/reference/csyncobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)