---
title: "accelerator_view, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::accelerator_view"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accelerator_view (classe)"
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
caps.latest.revision: 18
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# accelerator_view, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Représente une abstraction virtuelle de périphérique sur un accélérateur de données parallèle C\+\+ AMP.  
  
## Syntaxe  
  
```  
class accelerator_view;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[accelerator\_view::accelerator\_view, constructeur](../Topic/accelerator_view::accelerator_view%20Constructor.md)|Initialise une nouvelle instance de la classe `accelerator_view`.|  
|[accelerator\_view::~accelerator\_view, destructeur](../Topic/accelerator_view::~accelerator_view%20Destructor.md)|Détruit l'objet `accelerator_view`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[accelerator\_view::create\_marker, méthode](../Topic/accelerator_view::create_marker%20Method.md)|Renvoie un futur pour suivre la fin de toutes les commandes soumises jusqu'alors à cet objet `accelerator_view`.|  
|[accelerator\_view::flush, méthode](../Topic/accelerator_view::flush%20Method.md)|Envoie toutes les commandes mises en file d'attente à l'objet `accelerator_view` de l'accélérateur pour l'exécution.|  
|[accelerator\_view::get\_accelerator, méthode](../Topic/accelerator_view::get_accelerator%20Method.md)|Retourne l'objet `accelerator` de l'objet `accelerator_view`.|  
|[accelerator\_view::get\_is\_auto\_selection, méthode](../Topic/accelerator_view::get_is_auto_selection%20Method.md)|Retourne une valeur booléenne qui indique si le runtime sélectionne automatiquement un accélérateur approprié lorsque l'objet `accelerator_view` est passé à [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md).|  
|[accelerator\_view::get\_is\_debug, méthode](../Topic/accelerator_view::get_is_debug%20Method.md)|Retourne une valeur booléenne qui indique si l'objet `accelerator_view` a la couche DEBUG activée pour le rapport d'erreurs étendu.|  
|[accelerator\_view::get\_queuing\_mode, méthode](../Topic/accelerator_view::get_queuing_mode%20Method.md)|Retourne le mode de mise en file d'attente pour l'objet `accelerator_view`.|  
|[accelerator\_view::get\_version, méthode](../Topic/accelerator_view::get_version%20Method.md)|Retourne la version de `accelerator_view`.|  
|[accelerator\_view::wait, méthode](../Topic/accelerator_view::wait%20Method.md)|Attend la fin de toutes les commandes envoyées à l'objet `accelerator_view`.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[accelerator\_view::operator\!\=, opérateur](../Topic/accelerator_view::operator!=%20Operator.md)|Compare cet objet `accelerator_view` avec un autre. Retourne `false` s'ils sont égaux, sinon retourne `true`.|  
|[accelerator\_view::operator\=, opérateur](../Topic/accelerator_view::operator=%20Operator.md)|Copie le contenu de l'objet `accelerator_view` spécifié dans cet objet.|  
|[accelerator\_view::operator\=\=, opérateur](../Topic/accelerator_view::operator==%20Operator.md)|Compare cet objet `accelerator_view` avec un autre. Retourne `true` s'ils sont égaux, sinon retourne `false`.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[accelerator\_view::accelerator, données membres](../Topic/accelerator_view::accelerator%20Data%20Member.md)|Obtient l'objet `accelerator` pour l'objet `accelerator_view`.|  
|[accelerator\_view::is\_auto\_selection, membre de données](../Topic/accelerator_view::is_auto_selection%20Data%20Member.md)|Obtient une valeur booléenne qui indique si le runtime sélectionne automatiquement un accélérateur approprié lorsque l'objet `accelerator_view` est passé à [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md).|  
|[accelerator\_view::is\_debug, données membres](../Topic/accelerator_view::is_debug%20Data%20Member.md)|Obtient une valeur booléenne qui indique si l'objet `accelerator_view` a la couche DEBUG activée pour le rapport d'erreurs étendu.|  
|[accelerator\_view::queuing\_mode, données membres](../Topic/accelerator_view::queuing_mode%20Data%20Member.md)|Obtient le mode de mise en file d'attente pour l'objet `accelerator_view`.|  
|[accelerator\_view::version, données membres](../Topic/accelerator_view::version%20Data%20Member.md)|Obtient la version de l'accélérateur.|  
  
## Hiérarchie d'héritage  
 `accelerator_view`  
  
## Remarques  
 Un objet `accelerator_view` représente une vue logique et isolée d'un accélérateur.  Un périphérique physique de calcul peut avoir de nombreux objets `accelerator_view` logiques et isolés.  Chaque accélérateur un objet `accelerator_view` par défaut.  Des objets `accelerator_view` supplémentaires peuvent être créés.  
  
 les périphériques physiques peuvent être partagés entre de nombreux threads clients.  Les threads clients peuvent de manière coopérative utiliser le même objet `accelerator_view` d'un accélérateur, ou chaque client peut communiquer avec un périphérique de calcul via un objet indépendant `accelerator_view` pour l'isolation avec d'autres threads clients.  
  
 Un objet `accelerator_view` peut avoir l'une des deux états de [Énumération queuing\_mode](../../../parallel/amp/reference/queuing-mode-enumeration.md).  Si le mode mise en file d'attente est `immediate`, les commandes comme `copy` et `parallel_for_each` sont envoyées au périphérique accélérateur correspondant dès qu'elles reviennent à l'appelant.  Si le mode mise en file d'attente est `deferred`, ces commandes sont mises en file d'attente sur une file d'attente de commande qui correspond à l'objet `accelerator_view`.  Les commandes ne sont pas envoyées au périphérique jusqu'à ce que `flush()` soit appelé.  
  
## Configuration requise  
 **En\-tête :** amprt.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)