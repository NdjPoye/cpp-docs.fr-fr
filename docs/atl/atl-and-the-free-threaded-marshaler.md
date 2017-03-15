---
title: "ATL et le marshaleur libre de threads | Microsoft Docs"
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
  - "ATL, marshaleur libre de threads (FTM)"
  - "marshaleur libre de threads (FTM)"
  - "Intégration du format FTM au format ATL"
  - "threads (ATL), marshaleur libre de threads (FTM)"
  - "threads (C++), marshaleur dans ATL"
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL et le marshaleur libre de threads
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La page des attributs de l'assistant objet simple ATL fournit une option qui permet à votre classe pour agréger le marshaleur libre de threads \(FTM\).  
  
 l'assistant génère le code pour créer une instance du marshaleur libre de threads dans `FinalConstruct` et pour libérer cette instance dans `FinalRelease`.  Une macro d' `COM_INTERFACE_ENTRY_AGGREGATE` est ajoutée automatiquement au mappage COM pour garantir que les demandes d' `QueryInterface` pour [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707) sont traitées par le marshaleur libre de threads.  
  
 Le marshaleur libre de threads permet l'accès direct aux interfaces sur votre objet de tout thread dans le même de processus, accélérant des appels d'intercloisonnement.  Cette option est destinée aux classes qui utilisent les deux modèle de thread.  
  
 En utilisant cette option, les classes doivent être responsable de la sécurité des threads de leurs données.  En outre, les objets qui regroupent le marshaleur libre de threads et la nécessité d'utiliser des pointeurs d'interface obtenus à partir de autres objets doit prendre des mesures supplémentaires pour garantir que les interfaces sont correctement marshalées.  Cela implique généralement stocker des pointeurs d'interface dans le tableau global interface \(GIT\) et obtenir le pointeur de la table GIT chaque fois qu'il est utilisé.  ATL fournit la classe [CComGITPtr](../atl/reference/ccomgitptr-class.md) pour vous aider à des pointeurs d'interface d'utilisation stockés dans la table GIT.  
  
## Voir aussi  
 [Concepts](../atl/active-template-library-atl-concepts.md)   
 [CoCreateFreeThreadedMarshaler](http://msdn.microsoft.com/library/windows/desktop/ms694500)   
 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707)   
 [When to Use the Global Interface Table](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [In\-Process Server Threading Issues](http://msdn.microsoft.com/library/windows/desktop/ms687205)