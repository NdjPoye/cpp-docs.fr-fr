---
title: "Generics and Templates (Visual C++) | Microsoft Docs"
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
  - "generics [C++], vs. templates"
  - "templates, C++"
ms.assetid: 63adec79-b1dc-4a1a-a21d-b8a72a8fce31
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Generics and Templates (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les génériques et les modèles sont des fonctionnalités de langage qui assurent la prise en charge des types paramétrés.  Toutefois, elles sont différentes et ont différentes utilisations.  Cette rubrique propose une vue d'ensemble des nombreuses differences.  
  
 Pour plus d’informations, consultez [Windows Runtime and Managed Templates](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md) et [Vue d'ensemble des modèles](../Topic/Templates%20Overview.md).  
  
## Comparer des modèles et les génériques  
 Différences clés entre les génériques et les templates C\+\+:  
  
-   Les génériques sont génériques jusqu'à ce que les types soient substitués eux au moment de l'exécution.  Les modèles sont spécialisés au moment de la compilation pour qu'ils ne soient plus des types paramétrables au moment de l'exécution  
  
-   Le CLR prend en charge spécifiquement les génériques dans le langage MSIL.  Étant donné que le runtime connait les génériques, les types spécifiques peuvent être substitués en types génériques en faisant référence à un assembly qui contient un type générique.  Les modèles, en revanche, se change en types ordinaires au moment de la compilation et les types résultant ne peuvent être spécialisés dans d'autres assemblys.  
  
-   Les génériques spécialisés dans deux assemblys distincts avec les mêmes arguments de type sont du même type.  Les modèles spécialisés dans deux assemblys distincts avec les mêmes arguments de type sont considérées par le runtime comme étant des types différents.  
  
-   Les génériques sont générés en une seule partie de code exécutable utilisé pour tous les arguments de type référence \(qui n'est pas vrai pour les types de valeur, qui ont une implémentation par type de valeur\).  Le compilateur JIT connait les génériques et peut optimiser le code pour la référence ou pour les types de valeur utilisés comme arguments de type.  Les modèles génèrent un code d'exécution distinct pour chaque spécialisation.  
  
-   Les génériques n'autorise pas les paramètres de modèle sans type, tels que `template <int i> C {}`.  Les modèles le permettent.  
  
-   Les génériques ne prennent pas en charge la spécialisation explicite, \(à savoir l'implémentation personnalisée d'un modèle pour un type spécifique\).  Les modèles, si.  
  
-   Les génériques ne prennent pas en charge la spécialisation partielle, \(à savoir l'implémentation personnalisée d'un sous\-ensemble des arguments de type\).  Les modèles, si.  
  
-   Les génériques n'autorisent pas le paramètre de type à être utilisé comme classe de base pour le type générique.  Les modèles, si.  
  
-   Les modèles prennent en charge les paramètres modèle\-modèle \(par exemple  `template<template<class T> class X> class MyClass`\), mais les génériques ne le font pas.  
  
## Combiner des modèles et des génériques  
  
-   La différence de base dans les génériques a des implications pour générer des applications qui combinent les modèles et les génériques.  Par exemple, supposez que vous possédez une classe de modèle pour lequel vous souhaitez créer un wrapper générique pour exposer ce modèle à d'autres langues comme générique.  Vous ne pouvez pas autoriser un génériqueà prendre un paramètre de type qu'il passe ensuite au modèle, puisque le modèle doit posséder ce paramètre de type au moment de la compilation, mais le générique ne va pas résoudre le paramètre de type avant l'exécution.  L'imbrication d'un modèle dans un générique ne fonctionnera pas non plus parce qu'il n'existe aucun moyen de développer des modèles de compilation pour les types génériques aléatoires qui peuvent être instanciés au moment de l'exécution.  
  
## Exemple  
  
### Description  
 L'exemple suivant montre un exemple simple de modèles et de génériques d'utilisation ensemble.  Dans cet exemple, la classe du modèle passe le paramètre au type générique.  L'inverse n'est pas possible.  
  
 Cet idiome peut être utilisée lorsque vous souhaitez générer sur une API générique existante avec le code du modèle local à un assembly Visual C\+\+, ou lorsque vous devez ajouter une couche supplémentaire de paramétrage à un type générique, pour tirer profit de certaines fonctionnalités des modèles non pris en charge par les génériques.  
  
### Code  
  
```  
// templates_and_generics.cpp  
// compile with: /clr  
using namespace System;  
  
generic <class ItemType>  
ref class MyGeneric {  
   ItemType m_item;  
  
public:  
   MyGeneric(ItemType item) : m_item(item) {}  
   void F() {   
      Console::WriteLine("F");   
   }  
};  
  
template <class T>  
public ref class MyRef {  
MyGeneric<T>^ ig;  
  
public:  
   MyRef(T t) {  
      ig = gcnew MyGeneric<T>(t);  
      ig->F();  
    }      
};  
  
int main() {  
   // instantiate the template  
   MyRef<int>^ mref = gcnew MyRef<int>(11);  
}  
```  
  
### Sortie  
  
```  
F  
```  
  
## Voir aussi  
 [Generics](../windows/generics-cpp-component-extensions.md)