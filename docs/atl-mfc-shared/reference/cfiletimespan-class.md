---
title: Classe de CFileTimeSpan | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::GetTimeSpan
- ATLTIME/ATL::CFileTimeSpan::SetTimeSpan
dev_langs:
- C++
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8a25bab65d9e5705a71eddde901e747c43a5a002
ms.lasthandoff: 02/24/2017

---
# <a name="cfiletimespan-class"></a>CFileTimeSpan (classe)
Cette classe fournit des méthodes pour la gestion des dates relatives et associés à un fichier de valeurs d’heure.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CFileTimeSpan
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|Constructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|Appelez cette méthode pour récupérer l’intervalle de temps à partir de la `CFileTimeSpan` objet.|  
|[CFileTimeSpan::SetTimeSpan](#settimespan)|Appelez cette méthode pour définir la durée de la `CFileTimeSpan` objet.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileTimeSpan::operator-](#operator_-)|Effectue une soustraction sur un `CFileTimeSpan` objet.|  
|[CFileTimeSpan::operator ! =](#operator_neq)|Compare deux objets `CFileTimeSpan` pour déterminer s'ils sont différents.|  
|[CFileTimeSpan::operator +](#operator_add)|Effectue l’addition sur un `CFileTimeSpan` objet.|  
|[CFileTimeSpan::operator +=](#operator_add_eq)|Effectue l’addition sur un `CFileTimeSpan` de l’objet et assigner le résultat à l’objet actuel.|  
|[CFileTimeSpan::operator&lt;](#operator_lt)|Compare deux `CFileTimeSpan` objets pour déterminer le plus petit.|  
|[CFileTimeSpan::operator&lt;=](#operator_lt_eq)|Compare deux `CFileTimeSpan` objets pour déterminer l’égalité ou le plus petit.|  
|[CFileTimeSpan::operator =](#operator_eq)|L’opérateur d’assignation.|  
|[CFileTimeSpan::operator =](#operator_-_eq)|Effectue une soustraction sur un `CFileTimeSpan` de l’objet et assigner le résultat à l’objet actuel.|  
|[CFileTimeSpan::operator ==](#operator_eq_eq)|Compare deux objets `CFileTimeSpan` pour déterminer s’ils sont égaux.|  
|[CFileTimeSpan::operator&gt;](#operator_gt)|Compare deux `CFileTimeSpan` objets pour déterminer le plus grand.|  
|[CFileTimeSpan::operator&gt;=](#operator_gt_eq)|Compare deux `CFileTimeSpan` objets pour déterminer l’égalité ou la plus grande.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe fournit des méthodes pour la gestion des périodes relatifs souvent rencontrés lors des opérations quand un fichier a été créé, du dernier accès au ou dernière modification. Les méthodes de cette classe sont fréquemment utilisés conjointement avec [CFileTime classe](../../atl-mfc-shared/reference/cfiletime-class.md) objets.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple de [CFileTime::Millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atltime.h  
  
##  <a name="cfiletimespan"></a>CFileTimeSpan::CFileTimeSpan  
 Constructeur.  
  
```
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan` existant.  
  
 `nSpan`  
 Une période de temps en millisecondes.  
  
### <a name="remarks"></a>Notes  
 Le `CFileTimeSpan` objet peut être créé à l’aide d’un fichier `CFileTimeSpan` de l’objet ou exprimé comme une valeur 64 bits. Le constructeur par défaut définit l’intervalle de temps à 0.  
  
##  <a name="gettimespan"></a>CFileTimeSpan::GetTimeSpan  
 Appelez cette méthode pour récupérer l’intervalle de temps à partir de la `CFileTimeSpan` objet.  
  
```
LONGLONG GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie l’intervalle de temps en millisecondes.  
  
##  <a name="operator_-"></a>CFileTimeSpan::operator-  
 Effectue une soustraction sur un **CFileTimeSpan** objet.  
  
```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un `CFileTimeSpan` objet représentant le résultat de la différence entre les deux intervalles de temps.  
  
##  <a name="operator_neq"></a>CFileTimeSpan::operator ! =  
 Compare deux objets `CFileTimeSpan` pour déterminer s'ils sont différents.  
  
```
bool operator!=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si l’élément en cours de comparaison n’est pas égale à la `CFileTimeSpan` objet ; sinon **false**.  
  
##  <a name="operator_add"></a>CFileTimeSpan::operator +  
 Effectue l’addition sur un `CFileTimeSpan` objet.  
  
```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un `CFileTimeSpan` contenant la somme de la durée de deux étendues de l’objet.  
  
##  <a name="operator_add_eq"></a>CFileTimeSpan::operator +=  
 Effectue l’addition sur un `CFileTimeSpan` de l’objet et assigne le résultat à l’objet actuel.  
  
```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la mise à jour `CFileTimeSpan` contient la somme de la durée de deux étendues de l’objet.  
  
##  <a name="operator_lt"></a>CFileTimeSpan::operator&lt;  
 Compare deux `CFileTimeSpan` objets pour déterminer le plus petit.  
  
```
bool operator<(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si le premier objet est inférieure (autrement dit, représente une période plus courte) que le second, sinon **false**.  
  
##  <a name="operator_lt_eq"></a>CFileTimeSpan::operator&lt;=  
 Compare deux `CFileTimeSpan` objets pour déterminer l’égalité ou le plus petit.  
  
```
bool operator<=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si le premier objet est inférieur à (autrement dit, représente une période plus courte) ou égal au second, sinon **false**.  
  
##  <a name="operator_eq"></a>CFileTimeSpan::operator =  
 L’opérateur d’assignation.  
  
```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la mise à jour `CFileTimeSpan` objet.  
  
##  <a name="operator_-_eq"></a>CFileTimeSpan::operator =  
 Effectue une soustraction sur un `CFileTimeSpan` de l’objet et assigne le résultat à l’objet actuel.  
  
```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la mise à jour `CFileTimeSpan` objet.  
  
##  <a name="operator_eq_eq"></a>CFileTimeSpan::operator ==  
 Compare deux objets `CFileTimeSpan` pour déterminer s’ils sont égaux.  
  
```
bool operator==(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si les objets sont égaux, sinon **false**.  
  
##  <a name="operator_gt"></a>CFileTimeSpan::operator&gt;  
 Compare deux `CFileTimeSpan` objets pour déterminer le plus grand.  
  
```
bool operator>(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si le premier objet est supérieur à (autrement dit, représente une période plus longue) que le second, sinon **false**.  
  
##  <a name="operator_gt_eq"></a>CFileTimeSpan::operator&gt;=  
 Compare deux `CFileTimeSpan` objets pour déterminer l’égalité ou la plus grande.  
  
```
bool operator>=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si le premier objet est supérieur à (autrement dit, représente une période plus longue) ou égal au second, sinon **false**.  
  
##  <a name="settimespan"></a>CFileTimeSpan::SetTimeSpan  
 Appelez cette méthode pour définir la durée de la `CFileTimeSpan` objet.  
  
```
void SetTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nSpan`  
 La nouvelle valeur pour l’intervalle de temps en millisecondes.  
  
## <a name="see-also"></a>Voir aussi  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTime (classe)](../../atl-mfc-shared/reference/cfiletime-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [ATL et MFC des Classes partagées](../../atl-mfc-shared/atl-mfc-shared-classes.md)



