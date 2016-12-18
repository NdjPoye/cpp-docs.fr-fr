---
title: "typename | Microsoft Docs"
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
  - "typename"
  - "typename_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "spécificateur de modèle de nom de type"
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
caps.latest.revision: 7
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# typename
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique au compilateur qu'un identificateur inconnu est un type.  
  
## Syntaxe  
  
```  
  
typename identifier;  
```  
  
## Notes  
 Utilisez ce mot clé uniquement dans les définitions de modèle.  
  
 Ce mot clé doit être utilisé si le nom est un nom dépendant qualifié dans un argument template. Il est facultatif si le nom qualifié n'est pas dépendant.  Pour plus d'informations, consultez [Modèles et résolution de noms](../cpp/templates-and-name-resolution.md).  
  
 Le mot clé **typename** peut être utilisé par tout type n'importe où dans une déclaration ou définition de modèle.  Il n'est pas autorisé dans la liste des classes de base sauf sous forme d'argument template pour une classe de base de modèle.  
  
```  
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 Le mot clé **typename** peut également être utilisé à la place de **class** dans les listes de paramètres de modèle.  Par exemple, les instructions suivantes sont identiques :  
  
```  
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## Exemple  
  
```  
// typename.cpp  
template<class T> class X  
{  
   typename T::Y m_y;   // treat Y as a type  
};  
  
int main()  
{  
}  
```  
  
## Voir aussi  
 [Modèles](../cpp/templates-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)