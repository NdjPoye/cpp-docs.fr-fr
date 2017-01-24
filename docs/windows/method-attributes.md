---
title: "Method Attributes | Microsoft Docs"
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
  - "method attributes"
  - "attributes [C++], reference topics"
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Method Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

les attributs suivants s'appliquent aux méthodes dans une classe, une coclasse, ou une interface.  
  
|Attribut|Description|  
|--------------|-----------------|  
|[bindable](../windows/bindable.md)|Indique que la propriété prend en charge la liaison des données.|  
|[call\_as](../windows/call-as.md)|Permet à une fonction non à mapper à une fonction distante.|  
|[custom](../windows/custom-cpp.md)|Vous permet de définir votre propre attribut.|  
|[db\_column](../windows/db-column.md)|Lie une colonne spécifiée dans l'ensemble de lignes.|  
|[db\_command](../windows/db-command.md)|Crée une commande OLE DB.|  
|[db\_param](../windows/db-param.md)|associe la variable membre spécifiée avec une entrée ou un paramètre de sortie et délimite la variable.|  
|[db\_source](../windows/db-source.md)|crée une connexion à une source de données.|  
|[db\_table](../windows/db-table.md)|Ouvre une table OLE DB.|  
|[defaultbind](../windows/defaultbind.md)|Indique la propriété unique et pouvant être liée qui représente mieux l'objet.|  
|[defaultcollelem](../windows/defaultcollelem.md)|Utilisé pour l'optimisation du code Visual Basic.|  
|[displaybind](../windows/displaybind.md)|Indique une propriété qui doit être affichée à l'utilisateur comme pouvant être liée.|  
|[helpcontext](../windows/helpcontext.md)|Spécifie un ID de contexte qui laisse les informations de voir sur cet élément dans le fichier d'aide.|  
|[helpfile](../windows/helpfile.md)|définit le nom du fichier d'aide pour une bibliothèque de types.|  
|[helpstring](../windows/helpstring.md)|Spécifie une chaîne de caractères utilisée pour décrire l'élément auquel elle s'applique.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Spécifie l'ID d'une rubrique d'aide dans un fichier de .hlp ou .chm.|  
|[helpstringdll](../windows/helpstringdll.md)|Spécifie le nom de la DLL à utiliser pour effectuer la recherche de chaîne de document \(localisation\).|  
|[hidden](../windows/hidden.md)|Indique que l'élément existe mais ne doit pas être affiché dans un navigateur orienté utilisateur.|  
|[id](../windows/id.md)|Spécifie un DISPID d'une fonction membre \(une propriété ou une méthode, dans une interface ou dispinterface\).|  
|[immediatebind](../windows/immediatebind.md)|Indique qu'notifié immédiatement la base de données de toutes les modifications apportées à une propriété d'un objet lié aux données.|  
|[in](../windows/in-cpp.md)|Indique qu'un paramètre doit être passé de la procédure appelante jusqu'à la procédure appelée.|  
|[locales](../windows/local-cpp.md)|Vous permet d'utiliser le compilateur MIDL comme générateur d'en\-tête lorsqu'il est utilisé dans l'en\-tête d'interface.  Lorsqu'il est utilisé dans une fonction spécifique, indique une procédure locale pour laquelle un stub n'est généré.|  
|[nonbrowsable](../windows/nonbrowsable.md)|Indique qu'un membre d'interface ne doit pas être affiché dans l'Explorateur de propriétés.|  
|[propget](../windows/propget.md)|Spécifie une fonction accesseur de propriété.|  
|[propput](../windows/propput.md)|spécifie une fonction à paramètre de propriété.|  
|[propputref](../windows/propputref.md)|Spécifie une fonction à paramètre de propriété qui utilise une référence plutôt qu'une valeur.|  
|[prentice](../windows/ptr.md)|indique un pointeur comme pointeur complet.|  
|[plage](../windows/range-cpp.md)|Spécifie une plage de valeurs autorisées pour les arguments ou les champs dont les valeurs sont définies au moment de l'exécution.|  
|[requestedit](../windows/requestedit.md)|indique que la propriété prend en charge la notification d' **OnRequestEdit** .|  
|[restricted](../windows/restricted.md)|spécifie qu'un membre d'un module, d'une interface, ou d'une dispinterface ne peut pas être appelé arbitrairement.|  
|[satype](../windows/satype.md)|spécifie le type de données de la structure de **SAFEARRAY** .|  
|[source](../windows/source-cpp.md)|Spécifie les interfaces sources du contrôle sur les points de connexion sur une classe.  Sur une propriété ou une méthode, l'attribut source indique que le membre retourne un objet ou a VARIANT qui représentent une source d'événements.|  
|[synchronisez](../windows/synchronize.md)|synchronise l'accès à la méthode cible.|  
|[vararg](../windows/vararg.md)|Indique que la fonction prennent un nombre variable d'arguments.|  
  
## Voir aussi  
 [Attributes by Usage](../windows/attributes-by-usage.md)