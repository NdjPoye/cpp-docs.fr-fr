---
title: "_com_ptr_t, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_ptr_t (classe)"
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Un objet `_com_ptr_t` encapsule un pointeur d'interface COM et est appelé un pointeur « intelligent ».  Cette classe de modèle gère l'allocation et la désallocation des ressources via des appels de fonction aux fonctions membres **IUnknown** : `QueryInterface`, `AddRef` et **Release**.  
  
 Un pointeur intelligent est généralement référencé par la définition de typedef fournie par la macro **\_COM\_SMARTPTR\_TYPEDEF**.  Cette macro accepte un nom d'interface et l'IID et déclare une spécialisation de `_com_ptr_t` avec le nom de l'interface plus un suffixe `Ptr`.  Par exemple :  
  
```  
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
```  
  
 déclare la spécialisation `_com_ptr_t` **IMyInterfacePtr**.  
  
 Un ensemble de [modèles de fonction](../cpp/relational-function-templates.md), non membres de cette classe de modèle, prend en charge les comparaisons avec un pointeur intelligent à droite de l'opérateur de comparaison.  
  
### Construction  
  
|||  
|-|-|  
|[\_com\_ptr\_t](../cpp/com-ptr-t-com-ptr-t.md)|Construit un objet `_com_ptr_t`.|  
  
### Opérations de bas niveau  
  
|||  
|-|-|  
|[AddRef](../cpp/com-ptr-t-addref.md)|Appelle la fonction membre `AddRef` de **IUnknown** sur le pointeur d'interface encapsulé.|  
|[Attach](../cpp/com-ptr-t-attach.md)|Encapsule un pointeur d'interface brut du type de ce pointeur intelligent.|  
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|Crée une nouvelle instance d'un objet avec un **CLSID** ou **ProgID**.|  
|[Detach](../cpp/com-ptr-t-detach.md)|Extrait et retourne le pointeur d'interface encapsulé.|  
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|S'attache à une instance existante d'un objet doté d'un **CLSID** ou **ProgID**.|  
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|Retourne le pointeur d'interface encapsulé.|  
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|Appelle la fonction membre `QueryInterface` de **IUnknown** sur le pointeur d'interface encapsulé.|  
|[Release](../cpp/com-ptr-t-release.md)|Appelle la fonction membre **Release** de **IUnknown** sur le pointeur d'interface encapsulé.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../cpp/com-ptr-t-operator-equal.md)|Assigne une nouvelle valeur à un objet `_com_ptr_t` existant.|  
|[operators \=\=, \!\=, \<, \>, \<\=, \>\=](../cpp/com-ptr-t-relational-operators.md)|Comparent l'objet pointeur intelligent avec un autre pointeur intelligent, un pointeur d'interface brut ou **NULL**.|  
|[Extracteurs](../cpp/com-ptr-t-extractors.md)|Récupérez le pointeur d'interface COM encapsulé.|  
  
## FIN de la section spécifique à Microsoft  
  
## Configuration requise  
 **En\-tête :** comip.h  
  
 **Bibliothèque :** comsuppw.lib ou comsuppwd.lib \(voir [\/Zc:wchar\_t \(wchar\_t est un type natif\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) pour plus d'informations\)  
  
## Voir aussi  
 [Classes du support COM du compilateur](../cpp/compiler-com-support-classes.md)