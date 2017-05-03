---
title: "Platform::ArrayReference (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ArrayReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::ArrayReference (classe)"
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::ArrayReference (classe)
`ArrayReference` est un type d'optimisation que vous pouvez remplacer par [Platform::Array^](../cppcx/platform-array-class.md) dans les paramètres d'entrée lorsque vous souhaitez remplir un tableau de style C avec les données d'entrée.  
  
## Syntaxe  
  
```vb  
  
```  
  
```csharp  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[ArrayReference::ArrayReference, constructeur](../cppcx/arrayreference-arrayreference-constructor.md)|Initialise une nouvelle instance de la classe `ArrayReference`.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[ArrayReference::operator\(\), opérateur](../cppcx/arrayreference-operator-call-operator.md)|Convertit cette `ArrayReference` en une `Platform::Array<T>^*`.|  
|[ArrayReference::operator\=, opérateur](../cppcx/arrayreference-operator-assign-operator.md)|Assigne le contenu d'une autre `ArrayReference` à cette instance.|  
  
## Exceptions  
  
## Notes  
 En utilisant un `ArrayReference` pour remplir un tableau de style C, vous évitez l'opération de copie supplémentaire nécessaire en copiant d'abord vers une variable `Platform::Array`, puis dans le tableau de style C. Lorsque vous utilisez une `ArrayReference`, il n'existe qu'une seule opération de copie. Pour obtenir un exemple de code, consultez [Array et WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Titre de la sous\-section  
  
## Voir aussi  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)