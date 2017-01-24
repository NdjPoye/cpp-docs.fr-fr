---
title: "Attributs #import (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#import (directive), attributs"
ms.assetid: 2a5085e3-82ee-4f83-892b-0aa6cc13863b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Attributs #import (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fournit des liens vers des attributs utilisés avec la directive \#import.  
  
 **Section spécifique à Microsoft**  
  
 Les attributs ci\-dessous sont disponibles pour la directive \#import.  
  
|Attribut|Description|  
|--------------|-----------------|  
|[auto\_rename](../preprocessor/auto-rename.md)|Renomme des mots réservés C\+\+ en ajoutant deux traits de soulignement \(\_\_\) au nom de variable pour résoudre les conflits potentiels entre les noms.|  
|[auto\_search](../preprocessor/auto-search.md)|Spécifie que, lorsqu'une bibliothèque de types est référencée avec \#import et fait elle\-même référence à une autre bibliothèque de types, le compilateur peut effectuer une opération \#import implicite pour l'autre bibliothèque de types.|  
|[embedded\_idl](../preprocessor/embedded-idl.md)|Indique que la bibliothèque de types est écrite dans le fichier .tlh et que le code généré par attributs est conservé.|  
|[exclude](../preprocessor/exclude-hash-import.md)|Exclut des éléments des fichiers d'en\-tête de bibliothèque de types en cours de création.|  
|[high\_method\_prefix](../preprocessor/high-method-prefix.md)|Spécifie un préfixe à utiliser pour nommer les propriétés et les méthodes de haut niveau.|  
|[high\_property\_prefixes](../preprocessor/high-property-prefixes.md)|Spécifie d'autres préfixes pour trois méthodes de propriété.|  
|[implementation\_only](../preprocessor/implementation-only.md)|Supprime la génération du fichier d'en\-tête .tlh \(fichier d'en\-tête principal\).|  
|[include\(\)](../preprocessor/include-parens.md)|Désactive l'exclusion automatique.|  
|[inject\_statement](../preprocessor/inject-statement.md)|Insère son argument en tant que texte source dans l'en\-tête de bibliothèque de types.|  
|[named\_guids](../preprocessor/named-guids.md)|Indique au compilateur de définir et initialiser des variables GUID dans le style ancien, de la forme **LIBID\_MyLib**, **CLSID\_MyCoClass**, **IID\_MyInterface** et **DIID\_MyDispInterface**.|  
|[no\_auto\_exclude](../preprocessor/no-auto-exclude.md)|Désactive l'exclusion automatique.|  
|[no\_dual\_interfaces](../preprocessor/no-dual-interfaces.md)|Modifie la façon dont le compilateur génère des fonctions wrapper pour les méthodes d'interface double.|  
|[no\_implementation](../preprocessor/no-implementation.md)|Supprime la génération de l'en\-tête .tli, qui contient les implémentations des fonctions membres de wrapper.|  
|[no\_namespace](../preprocessor/no-namespace.md)|Indique que le nom de l'espace de noms n'est pas généré par le compilateur.|  
|[no\_registry](../preprocessor/no-registry.md)|Indique au compilateur de ne pas rechercher de bibliothèques de types dans le Registre.|  
|[no\_search\_namespace](../preprocessor/no-search-namespace.md)|Possède les mêmes fonctionnalités que l'attribut [no\_namespace](../preprocessor/no-namespace.md) mais est utilisé sur les bibliothèques de types dans lesquelles vous utilisez la directive \#import avec l'attribut [auto\_search](../preprocessor/auto-search.md).|  
|[no\_smart\_pointers](../preprocessor/no-smart-pointers.md)|Supprime la création des pointeurs intelligents pour toutes les interfaces dans la bibliothèque de types.|  
|[raw\_dispinterfaces](../preprocessor/raw-dispinterfaces.md)|Indique au compilateur de générer des fonctions wrapper de bas niveau pour les méthodes et les propriétés dispinterface qui appellent **IDispatch::Invoke** et retournent le code d'erreur `HRESULT`.|  
|[raw\_interfaces\_only](../preprocessor/raw-interfaces-only.md)|Supprime la génération des fonctions wrapper de gestion d'erreurs et des déclarations [propriété](../cpp/property-cpp.md) qui utilisent ces fonctions wrapper.|  
|[raw\_method\_prefix](../preprocessor/raw-method-prefix.md)|Spécifie un préfixe différent pour éviter les collisions de noms.|  
|[raw\_native\_types](../preprocessor/raw-native-types.md)|Désactive l'utilisation des classes de prise en charge COM dans les fonctions wrapper de haut niveau et force l'utilisation de types de données de bas niveau à la place.|  
|[raw\_property\_prefixes](../preprocessor/raw-property-prefixes.md)|Spécifie d'autres préfixes pour trois méthodes de propriété.|  
|[renommer](../preprocessor/rename-hash-import.md)|Offre une solution de contournement pour les problèmes de collisions de noms.|  
|[rename\_namespace](../preprocessor/rename-namespace.md)|Renomme l'espace de noms qui contient le contenu de la bibliothèque de types.|  
|[rename\_search\_namespace](../preprocessor/rename-search-namespace.md)|Possède les mêmes fonctionnalités que l'attribut [rename\_namespace](../preprocessor/rename-namespace.md) mais est utilisé sur les bibliothèques de types dans lesquelles vous utilisez la directive \#import avec l'attribut [auto\_search](../preprocessor/auto-search.md).|  
|[tlbid](../preprocessor/tlbid.md)|Permet de charger des bibliothèques autres que la bibliothèque de types principale.|  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)