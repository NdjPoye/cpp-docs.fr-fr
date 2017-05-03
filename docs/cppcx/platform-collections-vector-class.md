---
title: "Platform::Collections::Vector, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector (classe) (C++/Cx)"
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
caps.latest.revision: 17
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 17
---
# Platform::Collections::Vector, classe
Représente une collection séquentielle d'objets accessibles séparément par index.  
  
## Syntaxe  
  
```  
template <typename T, typename E>  
   ref class Vector sealed;  
```  
  
#### Paramètres  
 `T`  
 Type des éléments contenus dans l'objet Vector.  
  
 `E`  
 Spécifie un prédicat binaire pour tester l'égalité des valeurs de type `T`. La valeur par défaut est `std::equal_to<T>`.  
  
## Notes  
 Les types autorisés sont les suivants :  
  
1.  Entiers  
  
2.  Classe interface ^  
  
3.  Classe ref publique ^  
  
4.  value struct  
  
5.  classe d'énumération publique  
  
 La classe Vector est l'implémentation concrète C\+\+ de l'interface [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410).  
  
 Si vous tentez d'utiliser un type Vector dans une valeur ou un paramètre de retour public, l'erreur de compilateur C3986 est générée. Vous pouvez corriger l'erreur en modifiant le type du paramètre ou le type de la valeur de retour par [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410). Pour plus d'informations, consultez [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[Vector::Vector \(constructeur\)](../cppcx/vector-vector-constructor.md)|Initialise une nouvelle instance de la classe Vector.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[Vector::Append, méthode](../cppcx/vector-append-method.md)|Insère l'élément spécifié après le dernier élément du Vector actif.|  
|[Vector::Clear, méthode](../cppcx/vector-clear-method.md)|Supprime tous les éléments du vecteur actuel.|  
|[Vector::First \(méthode\)](../cppcx/vector-first-method.md)|Retourne un itérateur qui spécifie le premier élément du Vector.|  
|[Vector::GetAt \(méthode\)](../cppcx/vector-getat-method.md)|Récupère l'élément de l'objet Vector actuel qui est identifié par l'index spécifié.|  
|[Vector::GetMany \(méthode\)](../cppcx/vector-getmany-method.md)|Récupère une séquence d'éléments du Vector actif en commençant à l'index spécifié.|  
|[Vector::GetView \(méthode\)](../cppcx/vector-getview-method.md)|Retourne une vue en lecture seule d'un vecteur ; autrement dit, une [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md).|  
|[Vector::IndexOf \(méthode\)](../cppcx/vector-indexof-method.md)|Recherche l'élément spécifié dans l'objet Vector actuel, et s'il existe, retourne l'index de l'élément.|  
|[Vector::InsertAt, méthode](../cppcx/vector-insertat-method.md)|Insère l'élément spécifié dans le vecteur actuel après l'identification de l'élément par l'index spécifié.|  
|[Vector::ReplaceAll, méthode](../cppcx/vector-replaceall-method.md)|Supprime les éléments du Vector actif et les insère depuis le tableau spécifié.|  
|[Vector::RemoveAt, méthode](../cppcx/vector-removeat-method.md)|Supprime l'élément identifié par l'index spécifié à partir du Vector actif.|  
|[Vector::RemoveAtEnd, méthode](../cppcx/vector-removeatend-method.md)|Supprime l'élément à la fin du Vector actif.|  
|[Vector::SetAt, méthode](../cppcx/vector-setat-method.md)|Assigne la valeur spécifiée à l'élément du Vector actif identifié par l'index spécifié.|  
|[Vector::Size, méthode](../cppcx/vector-size-method.md)|Retourne le nombre d'éléments dans l'objet Vector actuel.|  
  
### Événements  
  
|||  
|-|-|  
|Nom|Description|  
|événement [Windows::Foundation::Collection::VectorChangedEventHandler\<T\>^ VectorChanged](http://go.microsoft.com/fwlink/p/?LinkId=262644)|Se produit lorsque le Vector est modifié.|  
  
## Hiérarchie d'héritage  
 `Vector`  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [\(NOTINBUILD\) Espace de noms Platform](http://msdn.microsoft.com/fr-fr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Création de composants Windows Runtime en C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)