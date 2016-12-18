---
title: "CRTThreadTraits Class | Microsoft Docs"
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
  - "ATL::CRTThreadTraits"
  - "ATL.CRTThreadTraits"
  - "CRTThreadTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRTThreadTraits class"
  - "threads (ATL), creation functions"
  - "threads (ATL), CRT threads"
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRTThreadTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit la fonction de création d'un thread CRT.  Utilisez cette classe si le thread utilise des fonctions CRT.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CRTThreadTraits  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRTThreadTraits::CreateThread](../Topic/CRTThreadTraits::CreateThread.md)|\(Statique\) appelle cette fonction pour créer un thread qui peut utiliser des fonctions CRT.|  
  
## Notes  
 Les caractéristiques de thread sont des classes qui fournissent une fonction de création d'un type particulier de thread.  La fonction de création a la même signature et sémantique que la fonction de [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) windows.  
  
 Les caractéristiques de thread sont utilisées par les classes suivantes :  
  
-   [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
-   [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 Si le thread n'utilise pas les fonctions CRT, utilisez [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md) à la place.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)