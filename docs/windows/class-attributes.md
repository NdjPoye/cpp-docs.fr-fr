---
title: "Class Attributes | Microsoft Docs"
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
  - "attributes [C++], class attributes"
  - "class attributes"
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Class Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

les attributs suivants s'appliquent à [classe](../cpp/class-cpp.md) C\+\+ le mot clé.  
  
|Attribut|Description|  
|--------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|indique que la classe prend en charge le regroupement.|  
|[agrégats](../windows/aggregates.md)|indique qu'un contrôle regroupe la classe cible.|  
|[appobject](../windows/appobject.md)|Identifie la coclasse comme un objet d'application, associé à une application complète .exe, et indique que les fonctions et les propriétés de la coclasse sont globalement disponibles à cette bibliothèque de types.|  
|[case](../windows/case-cpp.md)|utilisé avec l'attribut de [switch\_type](../windows/switch-type.md) dans une union.|  
|[coclasse](../windows/coclass.md)|crée un contrôle ActiveX.|  
|[com\_interface\_entry](../windows/com-interface-entry-cpp.md)|ajoute une entrée d'interface à un mappage COM.|  
|[Contrôle](../windows/control.md)|spécifie que le type défini par l'utilisateur est un contrôle.|  
|[custom](../windows/custom-cpp.md)|Vous permet de définir votre propre attribut.|  
|[db\_command](../windows/db-command.md)|Crée une commande OLE DB.|  
|[db\_param](../windows/db-param.md)|associe la variable membre spécifiée avec une entrée ou un paramètre de sortie et délimite la variable.|  
|[db\_source](../windows/db-source.md)|crée une connexion à une source de données.|  
|[db\_table](../windows/db-table.md)|Ouvre une table OLE DB.|  
|[par défaut](../windows/default-cpp.md)|Indique que le personnalisé ou la dispinterface définie dans une coclasse représente l'interface par défaut de programmabilité.|  
|[defaultvtable](../windows/defaultvtable.md)|Définit une interface en tant qu'interface vtable par défaut pour un contrôle.|  
|[event\_receiver](../windows/event-receiver.md)|crée un récepteur d'événements.|  
|[event\_source](../windows/event-source.md)|crée une source d'événement.|  
|[helpcontext](../windows/helpcontext.md)|Spécifie un ID de contexte qui laisse les informations de voir sur cet élément dans le fichier d'aide.|  
|[helpfile](../windows/helpfile.md)|définit le nom du fichier d'aide pour une bibliothèque de types.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Spécifie l'ID d'une rubrique d'aide dans un fichier de .hlp ou .chm.|  
|[helpstring](../windows/helpstring.md)|Spécifie une chaîne de caractères utilisée pour décrire l'élément auquel elle s'applique.|  
|[hidden](../windows/hidden.md)|Indique que l'élément existe mais ne doit pas être affiché dans un navigateur orienté utilisateur.|  
|[implements](../windows/implements-cpp.md)|Spécifie les interfaces de dispatch qui sont converties pour être des membres de la coclasse IDL.|  
|[implements\_category](../windows/implements-category.md)|Spécifie a implémenté des catégories de composants pour la classe.|  
|[module](../windows/module-cpp.md)|Définit le bloc bibliothèque dans le fichier .idl.|  
|[noncreatable](../windows/noncreatable.md)|définit un objet qui ne peut pas être instancié par lui\-même.|  
|[progid](../windows/progid.md)|définit l'identificateur programmatique pour un contrôle.|  
|[registration\_script](../windows/registration-script.md)|Exécute le script spécifié d'inscription.|  
|[requestedit](../windows/requestedit.md)|indique que la propriété prend en charge la notification d' **OnRequestEdit** .|  
|[source](../windows/source-cpp.md)|Spécifie les interfaces sources du contrôle sur les points de connexion sur une classe.  Sur une propriété ou une méthode, l'attribut source indique que le membre retourne un objet ou a VARIANT qui représentent une source d'événements.|  
|[support\_error\_information](../windows/support-error-info.md)|Prend en charge le rapport d'erreurs pour l'objet de la cible.|  
|[threads](../windows/threading-cpp.md)|spécifie le modèle de thread pour un contrôle.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Spécifie l'identificateur unique d'une classe ou une interface.|  
|[version](../windows/version-cpp.md)|Identifie une version particulière entre plusieurs versions d'une classe.|  
|[vi\_progid](../windows/vi-progid.md)|spécifie un formulaire indépendant de la version de l'identificateur programmatique.|  
  
## Voir aussi  
 [Attributes by Usage](../windows/attributes-by-usage.md)