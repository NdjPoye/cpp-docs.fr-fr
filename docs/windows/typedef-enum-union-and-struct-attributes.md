---
title: "Typedef, Enum, Union, and Struct Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "union attributes"
  - "attributes [C++], reference topics"
  - "struct attributes"
  - "typedef attributes"
  - "enum attributes"
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Typedef, Enum, Union, and Struct Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les attributs suivants s'appliquent à [typedef](http://msdn.microsoft.com/fr-fr/cc96cf26-ba93-4179-951e-695d1f5fdcf1), à [struct](../cpp/struct-cpp.md), et des mots clés d' [enum](../cpp/enumerations-cpp.md) C\+\+.  
  
### typedef  
  
|Attribut|Description|  
|--------------|-----------------|  
|[case](../windows/case-cpp.md)|utilisé avec l'attribut de [switch\_type](../windows/switch-type.md) dans **union**.|  
|[custom](../windows/custom-cpp.md)|Vous permet de définir votre propre attribut.|  
|[export](../windows/export.md)|Provoque une structure de données soient placées dans le fichier .idl.|  
|[first\_is](../windows/first-is.md)|Spécifie l'index du premier élément du tableau à transmettre.|  
|[helpcontext](../windows/helpcontext.md)|Spécifie un ID de contexte qui laisse les informations de voir sur cet élément dans le fichier d'aide.|  
|[helpfile](../windows/helpfile.md)|définit le nom du fichier d'aide pour une bibliothèque de types.|  
|[helpstring](../windows/helpstring.md)|Spécifie une chaîne de caractères utilisée pour décrire l'élément auquel elle s'applique.|  
|[library\_block](../windows/library-block.md)|Place un élément à l'intérieur de le bloc bibliothèque du fichier .idl.|  
|[prentice](../windows/ptr.md)|indique un pointeur comme pointeur complet.|  
|[public](../windows/public-cpp-attributes.md)|S'assurer qu'un typedef iront dans la bibliothèque de types même s'il n'est pas référencé du fichier .idl.|  
|[ref](../windows/ref-cpp.md)|identifie un pointeur de référence.|  
|[switch\_is](../windows/switch-is.md)|Spécifie l'expression ou l'identificateur agissant comme une union discriminante qui sélectionne le union.|  
|[switch\_type](../windows/switch-type.md)|Identifie le type de la variable utilisée comme une union discriminante.|  
|[unique](../windows/unique-cpp.md)|Spécifie un seul pointeur.|  
|[wire\_marshal](../windows/wire-marshal.md)|spécifie un type de données qui sera utilisé pour la transmission au lieu d'un type de données spécifique à l'application.|  
  
### enum  
  
|Attribut|Description|  
|--------------|-----------------|  
|[custom](../windows/custom-cpp.md)|Vous permet de définir votre propre attribut.|  
|[export](../windows/export.md)|Provoque une structure de données soient placées dans le fichier .idl.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Spécifie l'identificateur unique d'une classe ou une interface.|  
|[v1\_enum](../windows/v1-enum.md)|Règles que le type énuméré spécifié soit transmis comme une entité 32 bits, plutôt que la valeur par défaut 16 bits.|  
  
### union  
  
|Attribut|Description|  
|--------------|-----------------|  
|[custom](../windows/custom-cpp.md)|Vous permet de définir votre propre attribut.|  
|[export](../windows/export.md)|Provoque une structure de données soient placées dans le fichier .idl.|  
|[first\_is](../windows/first-is.md)|Spécifie l'index du premier élément du tableau à transmettre.|  
|[last\_is](../windows/last-is.md)|spécifie l'index du dernier élément de tableau à transmettre.|  
|[length\_is](../windows/length-is.md)|spécifie le nombre d'éléments de tableau à transmettre.|  
|[max\_is](../windows/max-is.md)|Indique la valeur maximale pour un index non valide de tableau.|  
|[size\_is](../windows/size-is.md)|Spécifie la taille de la mémoire allouée pour les pointeurs dimensionnés, les pointeurs dimensionnés aux pointeurs dimensionnés, et unique ou aux tableaux multidimensionnels.|  
|[unique](../windows/unique-cpp.md)|Spécifie un seul pointeur.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Spécifie l'identificateur unique d'une classe ou une interface.|  
  
### union de Nonencapsulated  
  
|Attribut|Description|  
|--------------|-----------------|  
|[ms\_union](../windows/ms-union.md)|Contrôle l'alignement de représentation des données de réseau les unions nonencapsulated.|  
|[no\_injected\_text](../windows/no-injected-text.md)|Le compilateur ne pourra pas d'injecter du code résultant de l'utilisation d'attributs.|  
  
### struct  
  
|Attribut|Description|  
|--------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|indique que la classe prend en charge le regroupement.|  
|[agrégats](../windows/aggregates.md)|indique qu'un contrôle regroupe la classe cible.|  
|[appobject](../windows/appobject.md)|Identifie la coclasse comme un objet d'application, associé à une application complète .exe, et indique que les fonctions et les propriétés de la coclasse sont globalement disponibles à cette bibliothèque de types.|  
|[coclasse](../windows/coclass.md)|crée un contrôle ActiveX.|  
|[com\_interface\_entry](../windows/com-interface-entry-cpp.md)|ajoute une entrée d'interface à un mappage COM.|  
|[Contrôle](../windows/control.md)|spécifie que le type défini par l'utilisateur est un contrôle.|  
|[custom](../windows/custom-cpp.md)|Vous permet de définir votre propre attribut.|  
|[db\_column](../windows/db-column.md)|Lie une colonne spécifiée dans l'ensemble de lignes.|  
|[db\_command](../windows/db-command.md)|Crée une commande OLE DB.|  
|[db\_param](../windows/db-param.md)|associe la variable membre spécifiée avec une entrée ou un paramètre de sortie et délimite la variable.|  
|[db\_source](../windows/db-source.md)|crée une connexion à une source de données.|  
|[db\_table](../windows/db-table.md)|Ouvre une table OLE DB.|  
|[par défaut](../windows/default-cpp.md)|Indique que le personnalisé ou la dispinterface définie dans une coclasse représente l'interface par défaut de programmabilité.|  
|[defaultvtable](../windows/defaultvtable.md)|Définit une interface en tant qu'interface vtable par défaut pour un contrôle.|  
|[event\_receiver](../windows/event-receiver.md)|crée un récepteur d'événements.|  
|[event\_source](../windows/event-source.md)|crée une source d'événement.|  
|[export](../windows/export.md)|Provoque une structure de données soient placées dans le fichier .idl.|  
|[first\_is](../windows/first-is.md)|Spécifie l'index du premier élément du tableau à transmettre.|  
|[hidden](../windows/hidden.md)|Indique que l'élément existe mais ne doit pas être affiché dans un navigateur orienté utilisateur.|  
|[implements\_category](../windows/implements-category.md)|Spécifie a implémenté des catégories de composants pour la classe.|  
|[last\_is](../windows/last-is.md)|spécifie l'index du dernier élément de tableau à transmettre.|  
|[length\_is](../windows/length-is.md)|spécifie le nombre d'éléments de tableau à transmettre.|  
|[max\_is](../windows/max-is.md)|Indique la valeur maximale pour un index non valide de tableau.|  
|[requires\_category](../windows/requires-category.md)|spécifie les catégories de composant requis de la classe cible.|  
|[size\_is](../windows/size-is.md)|Spécifie la taille de la mémoire allouée pour les pointeurs dimensionnés, les pointeurs dimensionnés aux pointeurs dimensionnés, et unique ou aux tableaux multidimensionnels.|  
|[source](../windows/source-cpp.md)|sur une classe, spécifie les interfaces sources de l'objet COM pour des points de connexion.  Sur une propriété ou une méthode, indique que le membre retourne un objet ou a VARIANT qui représentent une source d'événements.|  
|[threads](../windows/threading-cpp.md)|spécifie le modèle de thread pour un objet COM.|  
|[unique](../windows/unique-cpp.md)|Spécifie un seul pointeur.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Spécifie l'identificateur unique d'une classe ou une interface.|  
|[version](../windows/version-cpp.md)|Identifie une version particulière entre plusieurs versions d'une classe.|  
|[vi\_progid](../windows/vi-progid.md)|spécifie un formulaire indépendant de la version de l'identificateur programmatique.|  
  
## Voir aussi  
 [Attributes by Usage](../windows/attributes-by-usage.md)