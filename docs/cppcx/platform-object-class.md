---
title: "Platform::Object, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Object (classe)"
ms.assetid: 709e84a8-0bff-471b-bc14-63e424080b5a
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Platform::Object, classe
Fournit un comportement commun pour les classes ref et les structs ref dans les applications du Windows Store. Toute instance de classe ref ou de struct ref est implicitement convertible en objet Platform::Object^ et peut remplacer sa méthode ToString virtuelle.  
  
## Syntaxe  
  
```scr  
public ref class Object : Object  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[Object::Object, constructeur](../cppcx/object-object-constructor.md)|Initialise une nouvelle instance de la classe Object.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[Object::Equals, méthode](../cppcx/object-equals-method.md)|Détermine si l'objet spécifié est identique à l'objet actuel.|  
|[Object::GetHashCode, méthode](../cppcx/object-gethashcode-method.md)|Retourne le code de hachage de cette instance.|  
|[Object::ReferenceEquals, méthode](../cppcx/object-referenceequals-method.md)|Détermine si les instances Object spécifiées sont identiques.|  
|[ToString \(méthode\)](../cppcx/object-tostring-method-c-cx.md)|Retourne une chaîne qui représente l'objet actuel. Peut être substituée.|  
|[GetType, méthode](../cppcx/object-gettype-method.md)|Obtient un [Platform::Type](../cppcx/platform-type-class.md) qui décrit l'instance actuelle.|  
  
## Hiérarchie d'héritage  
 `Object`  
  
 `Object`  
  
## Configuration requise  
 **En\-tête** : vccorlib.h  
  
 **Espace de noms :** Platform  
  
## Voir aussi  
 [\(NOTINBUILD\) Espace de noms Platform](http://msdn.microsoft.com/fr-fr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)