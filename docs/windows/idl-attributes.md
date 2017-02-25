---
title: "IDL Attributes | Microsoft Docs"
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
  - "IDL attributes"
  - ".idl files, attributes"
  - "IDL files, attributes"
  - ".idl files"
ms.assetid: 04c596f4-c97b-4952-8053-316678b1d0b6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IDL Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Traditionnellement, maintenir un fichier .idl signifiait que vous deviez :  
  
-   Soyez familiarisé avec la structure et de la syntaxe d'un fichier .idl pouvoir le modifier.  
  
-   Appuyez sur un Assistant, qui vous laisserait modifier des aspects du fichier .idl.  
  
 Maintenant, vous pouvez modifier le fichier .idl d'un fichier de code source à l'aide de attributs Visual C\+\+ IDL.  Dans de nombreux cas, les attributs Visual C\+\+ IDL ont le même nom que les attributs de MIDL.  Lorsque le nom d'un attribut Visual C\+\+ IDL et un attribut de MIDL sont identiques, cela signifie que la mise de l'attribut Visual C\+\+ dans votre fichier de code source entraîne un fichier .idl qui contient son attribut de l'homonyme MIDL.  Toutefois, un attribut Visual C\+\+ IDL peut ne pas offrir toutes les fonctionnalités d'un attribut de MIDL.  
  
 Une fois non utilisés avec [Attributs COM](../windows/com-attributes.md), les attributs IDL vous permettent de définir des interfaces.  Lorsque le code source est compilé, les attributs sont utilisés pour définir le fichier généré .idl.  En cas de utilisation avec des attributs COM dans un projet ATL, attributs d'un certain IDL, tels que **coclasse**, le code de cause d'être injecté dans le projet.  
  
 Notez qu' [idl\_quote](../windows/idl-quote.md) vous permet d'utiliser les éléments de MIDL qui ne sont pas pris en charge dans la version actuelle de Visual C\+\+.  Ce point et d'autres attributs tels qu' [importlib](../windows/importlib.md) et [includelib](../windows/includelib-cpp.md) vous aident à utiliser ou les fichiers .idl dans votre projet Visual C\+\+ en cours.  
  
|Attribut|Description|  
|--------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|indique qu'un contrôle peut être regroupé par un autre contrôle.|  
|[appobject](../windows/appobject.md)|Identifie la coclasse comme un objet d'application, associé à une application complète EXE, et indique que les fonctions et les propriétés de la coclasse sont globalement disponibles à cette bibliothèque de types.|  
|[async\_uuid](../windows/async-uuid.md)|Spécifie UUID qui conduit le compilateur MIDL pour définir les versions synchrones et asynchrones pour une interface COM.|  
|[bindable](../windows/bindable.md)|Indique que la propriété prend en charge la liaison des données.|  
|[call\_as](../windows/call-as.md)|Permet à une fonction non à mapper à une fonction distante.|  
|[case](../windows/case-cpp.md)|utilisé avec l'attribut de [switch\_type](../windows/switch-type.md) dans une union.|  
|[coclasse](../windows/coclass.md)|Place la définition de classe dans un fichier .idl en tant que coclasse.|  
|[Contrôle](../windows/control.md)|spécifie que le type défini par l'utilisateur est un contrôle.|  
|[cpp\_quote](../windows/cpp-quote.md)|Effectue la chaîne spécifiée, sans guillemets, dans le fichier d'en\-tête généré.|  
|[defaultbind](../windows/defaultbind.md)|Indique la propriété unique et pouvant être liée qui représente mieux l'objet.|  
|[defaultcollelem](../windows/defaultcollelem.md)|Utilisé pour l'optimisation du code Visual Basic.|  
|[defaultvalue](../windows/defaultvalue.md)|Autorise la spécification d'une valeur par défaut pour un paramètre optionnel typé.|  
|[par défaut](../windows/default-cpp.md)|Indique que le personnalisé ou la dispinterface définie dans une coclasse représente l'interface par défaut de programmabilité.|  
|[defaultvtable](../windows/defaultvtable.md)|Définit une interface en tant qu'interface vtable par défaut pour un contrôle.|  
|[dispinterface](../windows/dispinterface.md)|Place une interface dans le fichier .idl en tant qu'interface de dispatch.|  
|[displaybind](../windows/displaybind.md)|Indique une propriété qui doit être affichée à l'utilisateur comme pouvant être liée.|  
|[dual](../windows/dual.md)|Place une interface dans le fichier .idl en tant qu'interface double.|  
|[entrée](../windows/entry.md)|Spécifie une fonction ou une constante exportée dans un module en identifiant le point d'entrée dans la DLL.|  
|[first\_is](../windows/first-is.md)|Spécifie l'index du premier élément du tableau à transmettre.|  
|[helpcontext](../windows/helpcontext.md)|Spécifie un ID de contexte qui laisse les informations de voir sur cet élément dans le fichier d'aide.|  
|[helpfile](../windows/helpfile.md)|définit le nom du fichier d'aide pour une bibliothèque de types.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Spécifie l'ID d'une rubrique d'aide dans un fichier de .hlp ou .chm.|  
|[helpstringdll](../windows/helpstringdll.md)|Spécifie le nom de la DLL à utiliser pour effectuer la recherche de chaîne de document \(localisation\).|  
|[helpstring](../windows/helpstring.md)|Spécifie une chaîne de caractères utilisée pour décrire l'élément auquel elle s'applique.|  
|[hidden](../windows/hidden.md)|Indique que l'élément existe mais ne doit pas être affiché dans un navigateur orienté utilisateur.|  
|[idl\_module](../windows/idl-module.md)|Spécifie un point d'entrée dans une DLL.|  
|[idl\_quote](../windows/idl-quote.md)|Vous permet de définir des attributs de utilisation ou aux éléments IDL qui ne sont pas pris en charge dans la version actuelle de Visual C\+\+.|  
|[id](../windows/id.md)|Spécifie un DISPID d'une fonction membre \(une propriété ou une méthode, dans une interface ou dispinterface\).|  
|[iid\_is](../windows/iid-is.md)|Spécifie l'IID de l'interface COM vers lequel un pointeur d'interface.|  
|[immediatebind](../windows/immediatebind.md)|Indique qu'notifié immédiatement la base de données de toutes les modifications apportées à une propriété d'un objet lié aux données.|  
|[importlib](../windows/importlib.md)|Rend les types qui ont déjà été compilés dans une autre bibliothèque de types disponible dans la bibliothèque de types est créée.|  
|[import](../windows/import.md)|Spécifie .idl, un .odl, ou un fichier d'en\-tête différent contenant des définitions que vous souhaitez référencer à partir de votre fichier principal .idl.|  
|[incluez](../windows/include-cpp.md)|Spécifie un ou plusieurs fichiers d'en\-tête à inclure dans le fichier généré .idl.|  
|[includelib](../windows/includelib-cpp.md)|Génère un fichier .idl ou .h à inclure dans le fichier généré .idl.|  
|[in](../windows/in-cpp.md)|Indique qu'un paramètre doit être passé de la procédure appelante jusqu'à la procédure appelée.|  
|[last\_is](../windows/last-is.md)|spécifie l'index du dernier élément de tableau à transmettre.|  
|[LCID](../windows/lcid.md)|Vous permet de passer un identificateur de paramètres régionaux à une fonction.|  
|[length\_is](../windows/length-is.md)|spécifie le nombre d'éléments de tableau à transmettre.|  
|[autorisé](../windows/licensed.md)|Indique que la coclasse à laquelle il s'applique est autorisée, et doit être instancié à l'aide de **IClassFactory2**.|  
|[locales](../windows/local-cpp.md)|Vous permet d'utiliser le compilateur MIDL comme générateur d'en\-tête lorsqu'il est utilisé dans l'en\-tête d'interface.  Lorsqu'il est utilisé dans une fonction spécifique, indique une procédure locale pour laquelle un stub n'est généré.|  
|[max\_is](../windows/max-is.md)|Indique la valeur maximale pour un index non valide de tableau.|  
|[module](../windows/module-cpp.md)|Définit le bloc bibliothèque dans le fichier .idl.|  
|[ms\_union](../windows/ms-union.md)|Contrôle l'alignement de représentation des données de réseau les unions nonencapsulated.|  
|[no\_injected\_text](../windows/no-injected-text.md)|Le compilateur ne pourra pas d'injecter du code résultant de l'utilisation d'attributs.|  
|[nonbrowsable](../windows/nonbrowsable.md)|Indique qu'un membre d'interface ne doit pas être affiché dans l'Explorateur de propriétés.|  
|[noncreatable](../windows/noncreatable.md)|définit un objet qui ne peut pas être instancié par lui\-même.|  
|[non extensible](../windows/nonextensible.md)|Spécifie que l'implémentation d' `IDispatch` inclut uniquement les propriétés et les méthodes figurant dans la description d'interface et ne peut pas être étendue avec les membres supplémentaires au moment de l'exécution.|  
|[object](../windows/object-cpp.md)|identifie une interface personnalisée ; synonyme d'attribut personnalisé.|  
|[\)](../windows/odl.md)|Identifie une interface en tant qu'interface \(ODL\) de langage\).|  
|[oleautomation](../windows/oleautomation.md)|Indique qu'une interface est compatible avec automation.|  
|[facultatif](../windows/optional-cpp.md)|spécifie un paramètre optionnel pour une fonction membre.|  
|[out](../windows/out-cpp.md)|Identifie les paramètres de pointeur qui sont retournés de la procédure appelée à la procédure appelante \(du serveur vers le client\).|  
|[pointer\_default](../windows/pointer-default.md)|Spécifie l'attribut par défaut de pointeur pour tous les pointeurs sauf les pointeurs de niveau supérieur qui apparaissent dans les listes de paramètres.|  
|[pragma](../windows/pragma.md)|Effectue la chaîne spécifiée, sans guillemets, dans le fichier généré .idl.|  
|[progid](../windows/progid.md)|spécifie l'identificateur programmatique pour un objet COM.|  
|[propget](../windows/propget.md)|Spécifie une fonction accesseur de propriété \(get\).|  
|[propputref](../windows/propputref.md)|Spécifie une fonction de paramètre de propriété qui utilise une référence plutôt qu'une valeur.|  
|[propput](../windows/propput.md)|spécifie une fonction de paramètre de propriété.|  
|[prentice](../windows/ptr.md)|indique un pointeur comme pointeur complet.|  
|[public](../windows/public-cpp-attributes.md)|S'assurer qu'un typedef iront dans la bibliothèque de types même s'il n'est pas référencé du fichier .idl.|  
|[plage](../windows/range-cpp.md)|Spécifie une plage de valeurs autorisées pour les arguments ou les champs dont les valeurs sont définies au moment de l'exécution.|  
|[readonly](../windows/readonly-cpp.md)|Interdit l'assignation à une variable.|  
|[ref](../windows/ref-cpp.md)|identifie un pointeur de référence.|  
|[requestedit](../windows/requestedit.md)|indique que la propriété prend en charge la notification d' **OnRequestEdit** .|  
|[restricted](../windows/restricted.md)|spécifie qu'une bibliothèque, ou le membre d'un module, d'une interface, ou d'une dispinterface ne peut pas être appelée arbitrairement.|  
|[retval](../windows/retval.md)|Indique le paramètre qui accepte la valeur de retour du membre.|  
|[size\_is](../windows/size-is.md)|Spécifie la taille de la mémoire allouée pour les pointeurs dimensionnés, les pointeurs dimensionnés aux pointeurs dimensionnés, et unique ou aux tableaux multidimensionnels.|  
|[source](../windows/source-cpp.md)|indique qu'un membre d'une classe, d'une propriété, ou d'une méthode est une source d'événements.|  
|[string](../windows/string-cpp.md)|Indique qu' `char`unidimensionnel, `wchar_t`, **byte**, ou tableau équivalente ou le pointeur à une telle tableau doivent être traités comme chaîne.|  
|[switch\_is](../windows/switch-is.md)|Spécifie l'expression ou l'identificateur agissant comme une union discriminante qui sélectionne le union.|  
|[switch\_type](../windows/switch-type.md)|Identifie le type de la variable utilisée comme une union discriminante.|  
|[transmit\_as](../windows/transmit-as.md)|Indique au compilateur d'associer un type présenté, que les applications client\-serveur manipulent, avec un type transmis.|  
|[uidefault](../windows/uidefault.md)|indique que le membre des informations de type est le membre par défaut pour l'affichage dans l'interface utilisateur.|  
|[unique](../windows/unique-cpp.md)|Spécifie un seul pointeur.|  
|[usesgetlasterror](../windows/usesgetlasterror.md)|Indique l'appelant que s'il existe une erreur en appelant cette fonction, l'appelant peut ensuite appeler `GetLastError` pour extraire le code d'erreur.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Spécifie l'identificateur unique d'une classe ou une interface.|  
|[v1\_enum](../windows/v1-enum.md)|Règles que le type énuméré spécifié soit transmis comme une entité 32 bits, plutôt que la valeur par défaut 16 bits.|  
|[vararg](../windows/vararg.md)|Indique que la fonction prennent un nombre variable d'arguments.|  
|[vi\_progid](../windows/vi-progid.md)|spécifie un formulaire indépendant de la version de l'identificateur programmatique.|  
|[wire\_marshal](../windows/wire-marshal.md)|spécifie un type de données qui sera utilisé pour la transmission au lieu d'un type de données spécifique à l'application.|  
  
## Voir aussi  
 [Attributes by Group](../windows/attributes-by-group.md)   
 [Attribute Limitations](http://msdn.microsoft.com/fr-fr/6e6c4329-f667-4869-b991-cbe9cb7a8f61)