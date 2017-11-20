---
title: "Les opérateurs ATL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs: C++
helpviewer_keywords: operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 46bc674a65e2ffc946a4806ce1440fec6e14c355
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="atl-operators"></a>Opérateurs d’ATL
Cette section contient les rubriques de référence pour les opérateurs globaux ATL.  
  
|Opérateur|Description|  
|--------------|-----------------|  
|[opérateur ==](#operator_eq_eq)|Compare deux `CSid` objets ou `SID` structures sont égales.|  
|[opérateur ! =](#operator_neq)|Compare deux `CSid` objets ou `SID` structures d’inégalité.|  
|[opérateur <](#operator_lt)|Teste si le `CSid` objet ou `SID` structure sur le côté gauche de l’opérateur est inférieure à la `CSid` objet ou `SID` structure sur le côté droit (pour la compatibilité de la bibliothèque C++ Standard).|  
|[opérateur >](#operator_gt)|Teste si le `CSid` objet ou `SID` structure sur le côté gauche de l’opérateur est supérieur à la `CSid` objet ou `SID` structure sur le côté droit (pour la compatibilité de la bibliothèque C++ Standard).|  
|[opérateur < =](#operator_lt__eq)|Teste si le `CSid` objet ou `SID` structure sur le côté gauche de l’opérateur est inférieur ou égal à la `CSid` objet ou `SID` structure sur le côté droit (pour la compatibilité de la bibliothèque C++ Standard).|  
|[opérateur > =](#operator_gt__eq)|Teste si le `CSid` objet ou `SID` structure sur le côté gauche de l’opérateur est supérieur ou égal à la `CSid` objet ou `SID` structure sur le côté droit (pour la compatibilité de la bibliothèque C++ Standard).|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlsecurity.h.  
  
##  <a name="operator_eq_eq"></a>opérateur ==  
 Compare `CSid` objets ou `SID` l’égalité des structures (identificateur de sécurité).  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Paramètres  
 `lhs`  
 La première `CSid` objet ou `SID` structure à comparer.  
  
 `rhs`  
 La seconde `CSid` objet ou `SID` structure à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si les objets sont égaux, **false** s’ils ne sont pas égaux.  
  
##  <a name="operator_neq"></a>opérateur ! =  
 Compare `CSid` objets ou `SID` inégalité des structures (identificateur de sécurité).  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Paramètres  
 `lhs`  
 La première `CSid` objet ou `SID` structure à comparer.  
  
 `rhs`  
 La seconde `CSid` objet ou `SID` structure à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si les objets ne sont pas égaux, **false** s’ils sont égaux.  
  
##  <a name="operator_lt"></a>opérateur <  
 Teste si le `CSid` objet ou `SID` structure sur le côté gauche de l’opérateur est inférieure à la `CSid` objet ou `SID` structure sur le côté droit (pour la compatibilité de la bibliothèque C++ Standard).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Paramètres  
 `lhs`  
 La première `CSid` objet ou `SID` structure à comparer.  
  
 `rhs`  
 La seconde `CSid` objet ou `SID` structure à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si l’adresse de la `lhs` objet est inférieur à l’adresse de la `rhs` objet, **false** dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Cet opérateur agit sur l’adresse de la `CSid` objet ou `SID` de la structure et est implémenté pour assurer la compatibilité avec les classes de collection de bibliothèque C++ Standard.  
  
##  <a name="operator_gt"></a>opérateur >  
 Teste si le `CSid` objet ou `SID` structure sur le côté gauche de l’opérateur est supérieur à la `CSid` objet ou `SID` structure sur le côté droit (pour la compatibilité de la bibliothèque C++ Standard).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Paramètres  
 `lhs`  
 La première `CSid` objet ou `SID` structure à comparer.  
  
 `rhs`  
 La seconde `CSid` objet ou `SID` structure à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si l’adresse de la `lhs` est supérieure à l’adresse de la `rhs`, **false** dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Cet opérateur agit sur l’adresse de la `CSid` objet ou `SID` de la structure et est implémenté pour assurer la compatibilité avec les classes de collection de bibliothèque C++ Standard.  
  
##  <a name="operator_lt__eq"></a>opérateur < =  
 Teste si le `CSid` objet ou `SID` structure sur le côté gauche de l’opérateur est inférieur ou égal à la `CSid` objet ou `SID` structure sur le côté droit (pour la compatibilité de la bibliothèque C++ Standard).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Paramètres  
 `lhs`  
 La première `CSid` objet ou `SID` structure à comparer.  
  
 `rhs`  
 La seconde `CSid` objet ou `SID` structure à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si l’adresse de la `lhs` est inférieur ou égal à l’adresse de la `rhs`, **false** dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Cet opérateur agit sur l’adresse de la `CSid` objet ou `SID` de la structure et est implémenté pour assurer la compatibilité avec les classes de collection de bibliothèque C++ Standard.  
  
##  <a name="operator_gt__eq"></a>opérateur > =  
 Teste si le `CSid` objet ou `SID` structure sur le côté gauche de l’opérateur est supérieur ou égal à la `CSid` objet ou `SID` structure sur le côté droit (pour la compatibilité de la bibliothèque C++ Standard).  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Paramètres  
 `lhs`  
 La première `CSid` objet ou `SID` structure à comparer.  
  
 `rhs`  
 La seconde `CSid` objet ou `SID` structure à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si l’adresse de la `lhs` est supérieur ou égal à l’adresse de la `rhs`, **false** dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Cet opérateur agit sur l’adresse de la `CSid` objet ou `SID` de la structure et est implémenté pour assurer la compatibilité avec les classes de collection de bibliothèque C++ Standard.



