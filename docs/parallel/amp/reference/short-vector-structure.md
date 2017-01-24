---
title: "short_vector Structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_short_vectors/Concurrency::graphics::short_vector"
dev_langs: 
  - "C++"
ms.assetid: e4f50b8f-1150-437d-b58c-79c5fb883708
caps.latest.revision: 7
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# short_vector Structure
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Le short\_vector fournit les définitions metaprogramming qui sont utiles pour la programmation des vecteurs courts de manière générique.  
  
## Syntaxe  
  
```  
template<  
   typename _Scalar_type,  
   int _Size  
>  
struct short_vector;  
template<>  
struct short_vector<unsigned int, 1>;  
template<>  
struct short_vector<unsigned int, 2>;  
template<>  
struct short_vector<unsigned int, 3>;  
template<>  
struct short_vector<unsigned int, 4>;  
template<>  
struct short_vector<int, 1>;  
template<>  
struct short_vector<int, 2>;  
template<>  
struct short_vector<int, 3>;  
template<>  
struct short_vector<int, 4>;  
template<>  
struct short_vector<float, 1>;  
template<>  
struct short_vector<float, 2>;  
template<>  
struct short_vector<float, 3>;  
template<>  
struct short_vector<float, 4>;  
template<>  
struct short_vector<unorm, 1>;  
template<>  
struct short_vector<unorm, 2>;  
template<>  
struct short_vector<unorm, 3>;  
template<>  
struct short_vector<unorm, 4>;  
template<>  
struct short_vector<norm, 1>;  
template<>  
struct short_vector<norm, 2>;  
template<>  
struct short_vector<norm, 3>;  
template<>  
struct short_vector<norm, 4>;  
template<>  
struct short_vector<double, 1>;  
template<>  
struct short_vector<double, 2>;  
template<>  
struct short_vector<double, 3>;  
template<>  
struct short_vector<double, 4>;  
```  
  
#### Paramètres  
 `_Scalar_type`  
 `_Size`  
  
## Membres  
  
### Typedefs publics  
  
|Name|Description|  
|----------|-----------------|  
|`type`||  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[short\_vector::short\_vector, constructeur](../Topic/short_vector::short_vector%20Constructor.md)||  
  
## Hiérarchie d'héritage  
 `short_vector`  
  
## Configuration requise  
 **En\-tête:** amp\_short\_vectors.h  
  
 **Espace de noms :** Concurrency::graphics  
  
## Voir aussi  
 [Concurrency::graphics, espace de noms](../../../parallel/amp/reference/concurrency-graphics-namespace.md)