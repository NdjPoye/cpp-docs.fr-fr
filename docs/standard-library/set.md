---
title: '&lt;set&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<set>
- std::<set>
- <set>
dev_langs:
- C++
helpviewer_keywords:
- set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: a31b01acf239fb745cf666e3a1329ee6d92eb86e
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="ltsetgt"></a>&lt;set&gt;
Définit les classes de modèle de conteneur set et multiset et leurs modèles de prise en charge.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <set>  
  
```  
  
## <a name="members"></a>Membres  
  
### <a name="operators"></a>Opérateurs  
  
|Version set|Version multiset|Description|  
|-----------------|----------------------|-----------------|  
|[operator!= (set)](../standard-library/set-operators.md#op_neq)|[operator!= (multiset)](../standard-library/set-operators.md#op_neq)|Teste si l'objet set ou multiset situé à gauche de l'opérateur n'est pas égal à l'objet set ou multiset situé à droite.|  
|[operator< (set)](../standard-library/set-operators.md#op_lt)|[operator< (multiset)](../standard-library/set-operators.md#op_lt_multiset)|Teste si l'objet set ou multiset situé à gauche de l'opérateur est inférieur à l'objet set ou multiset situé à droite.|  
|[operator<= (set)](../standard-library/set-operators.md#op_lt_eq)|[operator\<= (multiset)](../standard-library/set-operators.md#op_lt_eq_multiset)|Teste si l'objet set ou multiset situé à gauche de l'opérateur est inférieur ou égal à l'objet set ou multiset situé à droite.|  
|[operator== (set)](../standard-library/set-operators.md#op_eq_eq)|[operator== (multiset)](../standard-library/set-operators.md#op_eq_eq_multiset)|Teste si l'objet set ou multiset situé à gauche de l'opérateur est égal à l'objet set ou multiset situé à droite.|  
|[operator> (set)](../standard-library/set-operators.md#op_gt)|[operator> (multiset)](../standard-library/set-operators.md#op_gt_multiset)|Teste si l'objet set ou multiset situé à gauche de l'opérateur est supérieur à l'objet set ou multiset situé à droite.|  
|[operator>= (set)](../standard-library/set-operators.md#op_gt_eq)|[operator>= (multiset)](../standard-library/set-operators.md#op_gt_eq_multiset)|Teste si l'objet set ou multiset situé à gauche de l'opérateur est supérieur ou égal à l'objet set ou multiset situé à droite.|  
  
### <a name="specialized-template-functions"></a>Fonctions avec modèle spécialisé  
  
|Version set|Version multiset|Description|  
|-----------------|----------------------|-----------------|  
|[swap](../standard-library/set-functions.md#swap)|[swap (multiset)](../standard-library/set-functions.md#swap_multiset)|Échange les éléments de deux classes set ou multiset.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[set, classe](../standard-library/set-class.md)|Sert au stockage et à la récupération des données d’une collection dans laquelle les valeurs des éléments contenus sont uniques et servent de valeurs de clés en fonction desquelles les données sont automatiquement triées.|  
|[multiset, classe](../standard-library/multiset-class.md)|Sert au stockage et à la récupération des données d’une collection dans laquelle les valeurs des éléments contenus n’ont pas besoin d’être uniques et servent de valeurs de clés en fonction desquelles les données sont automatiquement triées.|  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)




