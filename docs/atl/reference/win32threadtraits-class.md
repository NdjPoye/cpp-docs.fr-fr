---
title: "Win32ThreadTraits Class | Microsoft Docs"
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
  - "Win32ThreadTraits"
  - "ATL::Win32ThreadTraits"
  - "ATL.Win32ThreadTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "threads (ATL), creation functions"
  - "threads (ATL), Windows threads"
  - "Win32ThreadTraits class"
ms.assetid: 50279c38-eae1-4301-9ea6-97ccea580f3e
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Win32ThreadTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit la fonction de création d'un thread windows.  Utilisez cette classe si le thread n'utilise pas les fonctions CRT.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class Win32ThreadTraits  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[Win32ThreadTraits::CreateThread](../Topic/Win32ThreadTraits::CreateThread.md)|\(Statique\) appelle cette fonction pour créer un thread qui ne doivent pas utiliser les fonctions CRT.|  
  
## Notes  
 Les caractéristiques de thread sont des classes qui fournissent une fonction de création d'un type particulier de thread.  La fonction de création a la même signature et sémantique que la fonction de [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) windows.  
  
 Les caractéristiques de thread sont utilisées par les classes suivantes :  
  
-   [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
-   [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 Si le thread utilise des fonctions CRT, utilisez [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) à la place.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)