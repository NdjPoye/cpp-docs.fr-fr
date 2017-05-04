---
title: "Platform::Array (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Array (classe)"
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Platform::Array (classe)
Représente un tableau unidimensionnel et modifiable qui peut être reçu et passé via l'interface binaire d'application \(ABI\).  
  
## Syntaxe  
  
```cpp  
  
template <typename T>  
    private ref class Array<TArg,1> :   
         public WriteOnlyArray<TArg, 1>,  
         public IBoxArray<TArg>  
  
```  
  
## Membres  
 Platform::Array hérite de toutes ses méthodes de [Platform::WriteOnlyArray \(classe\)](../cppcx/platform-writeonlyarray-class.md) et implémente la propriété `Value` de [Platform::IBoxArray, interface](../cppcx/platform-iboxarray-interface.md).  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[Constructeurs de tableaux](../cppcx/array-constructors.md)|Initialise un tableau unidimensionnel modifiable de types spécifiés par le paramètre de modèle de classe *T*.|  
  
### Méthodes  
 Consultez [Platform::WriteOnlyArray \(classe\)](../cppcx/platform-writeonlyarray-class.md).  
  
### Propriétés  
  
|||  
|-|-|  
|[Array::Value \(propriété\)](../cppcx/array-value-property.md)|Récupère un handle vers le tableau actuel.|  
  
## Notes  
 La classe Array est sealed et ne peut pas être héritée.  
  
 Le système de types Windows Runtime ne prend pas en charge le concept des tableaux en escalier et vous ne pouvez donc pas utiliser un IVector\<Platform::Array\<T\>\> comme valeur de retour ou paramètre de méthode. Pour passer un tableau en escalier ou une séquence de séquences à travers l'ABI, utilisez `IVector<IVector<T>^>`.  
  
 Pour plus d'informations sur le moment et la façon d'utiliser Platform::Array, consultez [Array et WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
 Le système de types Windows Runtime ne prend pas en charge le concept des tableaux en escalier et vous ne pouvez donc pas utiliser un IVector\<Platform::Array\<T\>\> comme valeur de retour ou paramètre de méthode. Pour passer un tableau en escalier ou une séquence de séquences à travers l'ABI, utilisez `IVector<IVector<T>^>`.  
  
 Cette classe est définie dans l'en\-tête vccorlib.h, qui est inclus automatiquement par le compilateur. Elle est visible dans Intellisense mais pas dans l'Explorateur d'objets, car elle n'est pas de type public défini dans platform.winmd.  
  
## Configuration requise  
 Option du compilateur : **\/ZW**  
  
## Voir aussi  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)   
 [Array et WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)