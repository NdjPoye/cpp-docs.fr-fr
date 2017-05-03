---
title: "Platform::WriteOnlyArray (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
s.suite: 
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::WriteOnlyArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::WriteOnlyArray (classe)"
ms.assetid: 92d7dd56-ec58-4b8c-88ba-9c903668b687
caps.latest.revision: 11
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 11
---
# Platform::WriteOnlyArray (classe)
Représente un tableau unidimensionnel utilisé comme paramètre d'entrée lorsque l'appelant transmet un tableau à remplir pour la méthode.  
  
 Cette classe ref est déclarée comme privée dans vccorlib.h. Par conséquent, elle n'est pas émise dans les métadonnées et est uniquement consommable à partir de C\+\+. Cette classe est prévue uniquement pour être utilisée comme paramètre d'entrée qui accepte un tableau que l'appelant a alloué. Elle n'est pas constructible à partir du code utilisateur. Il permet à la méthode C\+\+ d'écrire directement dans ce tableau, un modèle appelé modèle *FillArray*. Pour plus d'informations, consultez [Array et WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
## Syntaxe  
  
```cpp  
private ref class WriteOnlyArray<T, 1>  
```  
  
## Membres  
  
### M&\#233;thodes publiques  
 Ces méthodes offrent une accessibilité interne, c'est\-à\-dire qu'elles ne sont accessibles que dans l'application ou le composant C\+\+.  
  
|Nom|Description|  
|---------|-----------------|  
|[WriteOnlyArray::begin \(méthode\)](../cppcx/writeonlyarray-begin-method.md)|Itérateur qui pointe vers le premier élément du tableau.|  
|[WriteOnlyArray::Data, propriété](../cppcx/writeonlyarray-data-property.md)|Pointeur vers le tampon de données.|  
|[WriteOnlyArray::end \(méthode\)](../cppcx/writeonlyarray-end-method.md)|Itérateur qui pointe vers un élément au\-delà du dernier élément du tableau.|  
|[WriteOnlyArray::FastPass, propriété](../cppcx/writeonlyarray-fastpass-property.md)|Indique si le tableau peut utiliser le mécanisme FastPass, qui est une optimisation exécutée en toute transparence par le système. N'utilisez pas cela dans votre code|  
|[WriteOnlyArray::Length, propriété](../cppcx/writeonlyarray-length-property.md)|Retourne le nombre d'éléments du tableau.|  
|[WriteOnlyArray::set \(fonction\)](../cppcx/writeonlyarray-set-function.md)|Définit l'élément spécifié sur la valeur spécifiée.|  
  
## Hiérarchie d'héritage  
 `WriteOnlyArray`  
  
## Configuration requise  
 Option du compilateur : **\/ZW**  
  
 **Métadonnées :** platform.winmd  
  
 **Espace de noms :** Platform  
  
## Voir aussi  
 [\(NOTINBUILD\) Espace de noms Platform](http://msdn.microsoft.com/fr-fr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Création de composants Windows Runtime en C\+\+](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md)