---
title: "CCriticalSection Class | Microsoft Docs"
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
  - "CCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCriticalSection class"
  - "critical sections"
  - "classes de synchronisation, CCriticalSection class"
  - "synchronization objects, critical section"
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une section critique «  » — un objet de synchronisation qui permet à un seul thread à la fois pour accéder à une ressource ou une section de code.  
  
## Syntaxe  
  
```  
class CCriticalSection : public CSyncObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CCriticalSection::CCriticalSection](../Topic/CCriticalSection::CCriticalSection.md)|Construit un objet `CCriticalSection`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CCriticalSection::Lock](../Topic/CCriticalSection::Lock.md)|Utilisation d'accéder à l'objet d' `CCriticalSection` .|  
|[CCriticalSection::Unlock](../Topic/CCriticalSection::Unlock.md)|Libère l'objet d' `CCriticalSection` .|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CCriticalSection::operator CRITICAL\_SECTION\*](../Topic/CCriticalSection::operator%20CRITICAL_SECTION*.md)|Extrait un pointeur vers l'objet interne de **CRITICAL\_SECTION** .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CCriticalSection::m\_sect](../Topic/CCriticalSection::m_sect.md)|Un objet de **CRITICAL\_SECTION** .|  
  
## Notes  
 Les sections critiques sont utiles lorsqu'il peut permettre à un seul thread à la fois pour modifier les données ou une autre ressource contrôlée.  Par exemple, ajouter des nœuds à une liste liée est un processus qui doit être autorisé par un seul thread à la fois.  À l'aide d'un objet d' `CCriticalSection` pour contrôler la liste liée, un seul thread à la fois peut accéder à la liste.  
  
> [!NOTE]
>  Les fonctionnalités de la classe d' `CCriticalSection` est fournie par un objet réel Win32 **CRITICAL\_SECTION** .  
  
 Les sections critiques sont utilisées au lieu des mutex \(consultez [CMutex](../../mfc/reference/cmutex-class.md)\) lorsque la vitesse est critique et la ressource n'est pas utilisée au delà de les limites du processus.  
  
 Il existe deux méthodes pour utiliser un objet d' `CCriticalSection` : autonome et incorporé dans une classe.  
  
-   La méthode autonome pour utiliser un objet autonome d' `CCriticalSection` , construisent l'objet d' `CCriticalSection` lorsqu'elle est nécessaire.  Après qu'un retour réussi du constructeur, verrouillent explicitement l'objet avec un appel à [Verrouillage](../Topic/CCriticalSection::Lock.md).  Appelez [déverrouillez](../Topic/CCriticalSection::Unlock.md) lorsque vous avez fini accédant à la section critique.  Cette méthode, tandis que clearer à un utilisateur qui lit votre code source, est une erreur plus encline que vous devez penser à verrouiller et déverrouiller la section critique avant et après l'accès.  
  
     Une méthode plus est préférable d'utiliser la classe de [CSingleLock](../../mfc/reference/csinglelock-class.md) .  Elle possède également une méthode d' `Lock` et d' `Unlock` , mais vous n'avez pas à vous préoccuper de déverrouiller la ressource si une exception se produit.  
  
-   Méthode incorporée vous pouvez également partager une classe avec plusieurs threads en ajoutant une donnée membre de type d' `CCriticalSection`à la classe et le verrouillage le membre lorsque cela est nécessaire.  
  
 Pour plus d'informations sur l'utilisation des objets d' `CCriticalSection` , consultez l'article [Multithreading : Comment utiliser les classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CCriticalSection`  
  
## Configuration requise  
 **Header:** afxmt.h  
  
## Voir aussi  
 [CSyncObject Class](../../mfc/reference/csyncobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CMutex Class](../../mfc/reference/cmutex-class.md)