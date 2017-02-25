---
title: "Interface Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], reference topics"
  - "interface attributes"
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Interface Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

les attributs suivants s'appliquent à [interface \(ou \_\_interface\)](../cpp/interface.md) C\+\+ le mot clé.  
  
|Attribut|Description|  
|--------------|-----------------|  
|[async\_uuid](../windows/async-uuid.md)|Spécifie UUID qui conduit le compilateur MIDL pour définir les versions synchrones et asynchrones pour une interface COM.|  
|[custom](../windows/custom-cpp.md)|Vous permet de définir vos propres attributs.|  
|[dispinterface](../windows/dispinterface.md)|Place une interface dans le fichier .idl en tant qu'interface de dispatch.|  
|[dual](../windows/dual.md)|Place une interface dans le fichier .idl en tant qu'interface double.|  
|[export](../windows/export.md)|Provoque une structure de données soient placées dans le fichier .idl.|  
|[helpcontext](../windows/helpcontext.md)|Spécifie un ID de contexte qui laisse les informations de voir sur cet élément dans le fichier d'aide.|  
|[helpfile](../windows/helpfile.md)|définit le nom du fichier d'aide pour une bibliothèque de types.|  
|[helpstring](../windows/helpstring.md)|Spécifie une chaîne de caractères utilisée pour décrire l'élément auquel elle s'applique.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Spécifie l'ID d'une rubrique d'aide dans un fichier de .hlp ou .chm.|  
|[helpstringdll](../windows/helpstringdll.md)|Spécifie le nom de la DLL à utiliser pour effectuer la recherche de chaîne de document \(localisation\).|  
|[hidden](../windows/hidden.md)|Indique que l'élément existe mais ne doit pas être affiché dans un navigateur orienté utilisateur.|  
|[library\_block](../windows/library-block.md)|Place un élément à l'intérieur de le bloc bibliothèque du fichier .idl.|  
|[locales](../windows/local-cpp.md)|Vous permet d'utiliser le compilateur MIDL comme générateur d'en\-tête lorsqu'il est utilisé dans l'en\-tête d'interface.  Lorsqu'il est utilisé dans une fonction spécifique, indique une procédure locale pour laquelle un stub n'est généré.|  
|[non extensible](../windows/nonextensible.md)|Spécifie que l'implémentation d' `IDispatch` inclut uniquement les propriétés et les méthodes figurant dans la description d'interface et ne peut pas être étendue avec les membres supplémentaires au moment de l'exécution.  Cet attribut est uniquement valide sur une interface de [double](../windows/dual.md) .|  
|[\)](../windows/odl.md)|Identifie une interface en tant qu'interface \(ODL\) de langage\).|  
|[object](../windows/object-cpp.md)|identifie une interface personnalisée.|  
|[oleautomation](../windows/oleautomation.md)|Indique qu'une interface est compatible avec automation.|  
|[pointer\_default](../windows/pointer-default.md)|Spécifie l'attribut par défaut de pointeur pour tous les pointeurs sauf les pointeurs de niveau supérieur qui apparaissent dans les listes de paramètres.|  
|[prentice](../windows/ptr.md)|indique un pointeur comme pointeur complet.|  
|[restricted](../windows/restricted.md)|Indique les membres de la bibliothèque ne peuvent pas être appelées arbitrairement.|  
|[uuid](../windows/uuid-cpp-attributes.md)|fournit l'identificateur unique pour la bibliothèque|  
  
 Vous devez respecter ces règles pour définir une interface :  
  
-   la convention d'appel par défaut est [\_\_stdcall](../cpp/stdcall.md).  
  
-   GUID est fourni à votre place si vous ne fournissez pas de.  
  
-   Vous ne pouvez pas de méthode surchargée.  
  
 Sans spécifier l'attribut d' [uuid](../windows/uuid-cpp-attributes.md) et en n'utilisant pas le même nom de l'interface dans différents projets d'attribut, même GUID est généré.  
  
## Voir aussi  
 [Attributes by Usage](../windows/attributes-by-usage.md)