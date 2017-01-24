---
title: "CAdapt Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAdapt"
  - "ATL.CAdapt<T>"
  - "ATL::CAdapt"
  - "ATL::CAdapt<T>"
  - "CAdapt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& (opérateur), address-of (opérateur)"
  - "adapter objects"
  - "address-of (opérateur)"
  - "CAdapt class"
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAdapt Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce modèle permet d'inclure dans un wrapper les classes qui redéfinissent l'opérateur d'adresse afin de retourner un autre élément que l'adresse de l'objet.  
  
## Syntaxe  
  
```  
  
      template <  
   class T  
>  
class CAdapt  
```  
  
#### Paramètres  
 `T`  
 Type adapté.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAdapt::CAdapt](../Topic/CAdapt::CAdapt.md)|Constructeur.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAdapt::operator const T&](../Topic/CAdapt::operator%20const%20T&.md)|Retourne une référence `const` à `m_T`.|  
|[CAdapt::operator T&](../Topic/CAdapt::operator%20T&.md)|Retourne une référence à `m_T`.|  
|[CAdapt::operator \<](../Topic/CAdapt::operator%20%3C.md)|Compare un objet du type adapté à `m_T`.|  
|[CAdapt::operator \=](../Topic/CAdapt::operator%20=.md)|Assigne un objet du type adapté à `m_T`.|  
|[CAdapt::operator \=\=](../Topic/CAdapt::operator%20==.md)|Compare un objet du type adapté à `m_T`.|  
  
### Membres de données publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAdapt::m\_T](../Topic/CAdapt::m_T.md)|Données adaptées.|  
  
## Notes  
 `CAdapt` est un modèle simple qui permet d'inclure dans un wrapper les classes qui redéfinissent l'opérateur d'adresse \(`operator &`\) afin de retourner un autre élément que l'adresse de l'objet.  Parmi ces exemples de classes figurent les classes ATL `CComBSTR`, `CComPtr` et `CComQIPtr`, ainsi que la classe de prise en charge COM du compilateur, `_com_ptr_t`.  Ces classes redéfinissent toutes l'opérateur d'adresse afin de retourner l'adresse de l'un de leurs membres de données \(`BSTR` dans le cas de `CComBSTR`, et un pointeur d'interface dans le cas des autres classes\).  
  
 Le rôle principal de `CAdapt` est de masquer l'opérateur d'adresse défini par la classe `T` tout en conservant les caractéristiques de la classe adaptée.  `CAdapt` remplit ce rôle en détenant un membre public, [m\_T](../Topic/CAdapt::m_T.md), de type `T`, et en définissant des opérateurs de conversion, des opérateurs de comparaison et un constructeur de copie afin d'autoriser les spécialisations de `CAdapt` à être traitées comme si elles étaient des objets de type `T`.  
  
 La classe d'adaptateur `CAdapt` est utile, car certaines classes de type conteneur sont censées être capables d'obtenir les adresses des objets contenus via l'opérateur d'adresse.  La redéfinition de l'opérateur d'adresse peut confondre cette exigence, généralement en provoquant des erreurs de compilation et en empêchant l'utilisation du type non adapté avec les classes qui s'attendent à ce qu'il fonctionne « tout simplement ».  `CAdapt` permet de contourner ces problèmes.  
  
 En règle générale, utilisez `CAdapt` lorsque vous souhaitez stocker des objets `CComBSTR`, `CComPtr`, `CComQIPtr` ou `_com_ptr_t` dans une classe de type conteneur.  Ceci était le plus souvent nécessaire pour les conteneurs de bibliothèque standard C\+\+ avant la prise en charge de la norme C\+\+11. Toutefois, les conteneurs de bibliothèque standard C\+\+11 fonctionnent automatiquement avec les types ayant un `operator&()` surchargé.  La bibliothèque standard permet d'obtenir ce résultat en utilisant de façon interne [std::addressof\(\)](../Topic/addressof.md) pour obtenir les adresses réelles des objets.  
  
## Configuration requise  
 **En\-tête :** atlcomcli.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)