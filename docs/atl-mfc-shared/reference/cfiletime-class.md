---
title: Classe de CFileTime | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CFileTime
- CFileTime
- ATL.CFileTime
dev_langs:
- C++
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
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
ms.openlocfilehash: 5ff7abc32093691d230787e8eb2d859bb4e77428
ms.lasthandoff: 02/24/2017

---
# <a name="cfiletime-class"></a>CFileTime (classe)
Cette classe fournit des méthodes pour gérer les valeurs de date et heure associées à un fichier.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CFileTime :  public FILETIME
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileTime::CFileTime](#cfiletime)|Constructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileTime::GetCurrentTime](#getcurrenttime)|Appelez cette fonction statique pour récupérer une `CFileTime` objet qui représente l’heure et la date système actuelle.|  
|[CFileTime::GetTime](#gettime)|Appelez cette méthode pour récupérer l’heure à partir de la `CFileTime` objet.|  
|[CFileTime::LocalToUTC](#localtoutc)|Appelez cette méthode pour convertir une heure de fichier local à une heure de fichier basée sur le temps universel coordonné (UTC).|  
|[CFileTime::SetTime](#settime)|Appelez cette méthode pour définir la date et l’heure stockée par le `CFileTime` objet.|  
|[CFileTime::UTCToLocal](#utctolocal)|Appelez cette méthode pour convertir l’heure basée sur le temps universel coordonné (UTC) heure de fichier local.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileTime::operator-](#operator_-)|Cet opérateur est utilisé pour exécuter la soustraction sur un `CFileTime` ou `CFileTimeSpan` objet.|  
|[CFileTime::operator ! =](#operator_neq)|Cet opérateur compare deux `CFileTime` objets sont inégaux.|  
|[CFileTime::operator +](#operator_add)|Cet opérateur permet d'effectuer une addition sur un objet `CFileTimeSpan`.|  
|[CFileTime::operator +=](#operator_add_eq)|Cet opérateur permet d'effectuer une addition sur un objet `CFileTimeSpan` et d'assigner le résultat à l'objet actuel.|  
|[CFileTime::operator&lt;](#operator_lt)|Cet opérateur compare deux objets `CFileTime` pour déterminer le plus petit.|  
|[CFileTime::operator&lt;=](#operator_lt_eq)|Cet opérateur compare deux objets `CFileTime` pour déterminer le plus petit ou leur égalité.|  
|[CFileTime::operator =](#operator_eq)|L’opérateur d’assignation.|  
|[CFileTime::operator =](#operator_-_eq)|Cet opérateur est utilisé pour exécuter la soustraction sur un `CFileTimeSpan` de l’objet et assigner le résultat à l’objet actuel.|  
|[CFileTime::operator ==](#operator_eq_eq)|Cet opérateur compare deux objets `CFileTime` pour déterminer leur égalité.|  
|[CFileTime::operator&gt;](#operator_gt)|Cet opérateur compare deux objets `CFileTime` pour déterminer le plus grand.|  
|[CFileTime::operator&gt;=](#operator_gt_eq)|Cet opérateur compare deux objets `CFileTime` pour déterminer le plus grand ou leur égalité.|  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileTime::Day](#day)|Une donnée membre static stocker le nombre d’intervalles de 100 nanosecondes qui constituent un jour.|  
|[CFileTime::Hour](#hour)|Une donnée membre static stocker le nombre d’intervalles de 100 nanosecondes qui composent une heure.|  
|[CFileTime::Millisecond](#millisecond)|Une donnée membre static stocker le nombre d’intervalles de 100 nanosecondes qui composent une milliseconde.|  
|[CFileTime::Minute](#minute)|Une donnée membre static stocker le nombre d’intervalles de 100 nanosecondes qui composent une minute.|  
|[CFileTime::Second](#second)|Une donnée membre static stocker le nombre d’intervalles de 100 nanosecondes qui composent une seconde.|  
|[CFileTime::Week](#week)|Une donnée membre static stocker le nombre d’intervalles de 100 nanosecondes qui composent une semaine.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe fournit des méthodes pour gérer les valeurs de date et l’heure associées à la création, l’accès et la modification des fichiers. Les méthodes et les données de cette classe sont fréquemment utilisées conjointement avec `CFileTimeSpan` des objets, qui traitent des valeurs d’heure relative.  
  
 La valeur de date et d’heure est stockée comme une valeur 64 bits représentant le nombre d’intervalles de 100 nanosecondes depuis le 1er janvier 1601. Ceci est le format de temps universel coordonné (UTC).  
  
 Les variables membres const statiques suivantes sont fournies pour simplifier les calculs :  
  
|Variable membre|Nombre d’intervalles de 100 nanosecondes.|  
|---------------------|-----------------------------------------|  
|Milliseconde|10,000|  
|Seconde|Milliseconde * 1 000|  
|Minute|Deuxième * 60|  
|Heure|Minute * 60|  
|Jour|Heure * 24|  
|Semaine|Jour * 7|  
  
 **Remarque** pas tous les systèmes de fichiers peuvent enregistrer la création et heure de dernier accès et les systèmes de fichiers pas les enregistrent de la même manière. Par exemple, sur le système de fichiers FAT Windows NT, créez temps avec une résolution de 10 millisecondes, temps d’écriture avec une résolution de 2 secondes et temps d’accès présente une résolution de 1 jour (date d’accès). Sur NTFS, temps d’accès a une résolution de 1 heure. En outre, FAT enregistre le temps sur le disque en heure locale, mais NTFS enregistre la fois sur le disque au format UTC. Pour plus d’informations, consultez [temps](http://msdn.microsoft.com/library/windows/desktop/ms724290).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `FILETIME`  
  
 `CFileTime`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atltime.h  
  
##  <a name="a-namecfiletimea--cfiletimecfiletime"></a><a name="cfiletime"></a>CFileTime::CFileTime  
 Constructeur.  
  
```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `ft`  
 A [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) structure.  
  
 `nTime`  
 Date et heure exprimées sous forme d’une valeur 64 bits.  
  
### <a name="remarks"></a>Remarques  
 Le `CFileTime` objet peut être créé à l’aide d’une date existante et l’heure dans un `FILETIME` structurer ou exprimé comme une valeur 64 bits (en local ou de formats d’heure temps universel coordonné (UTC)). Le constructeur par défaut définit l’heure à 0.  
  
##  <a name="a-namedaya--cfiletimeday"></a><a name="day"></a>CFileTime::Day  
 Une donnée membre static stocker le nombre d’intervalles de 100 nanosecondes qui constituent un jour.  
  
```
static const ULONGLONG Day = Hour* 24;
```  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CFileTime::Millisecond](#millisecond).  
  
##  <a name="a-namegetcurrenttimea--cfiletimegetcurrenttime"></a><a name="getcurrenttime"></a>CFileTime::GetCurrentTime  
 Appelez cette fonction statique pour récupérer une `CFileTime` objet qui représente l’heure et la date système actuelle.  
  
```
static CFileTime GetCurrentTime() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la date système actuelle et l’heure au format de temps universel coordonné (UTC).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[# NVC_MFCFiles&41;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]  
  
##  <a name="a-namegettimea--cfiletimegettime"></a><a name="gettime"></a>CFileTime::GetTime  
 Appelez cette méthode pour récupérer l’heure à partir de la `CFileTime` objet.  
  
```
ULONGLONG GetTime() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la date et l’heure sous la forme d’un nombre 64 bits, ce qui peut être au format de temps universel coordonné (UTC) ou local.  
  
##  <a name="a-namehoura--cfiletimehour"></a><a name="hour"></a>CFileTime::Hour  
 Une donnée membre static stocker le nombre d’intervalles de 100 nanosecondes qui composent une heure.  
  
```
static const ULONGLONG Hour = Minute* 60;
```  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CFileTime::Millisecond](#millisecond).  
  
##  <a name="a-namelocaltoutca--cfiletimelocaltoutc"></a><a name="localtoutc"></a>CFileTime::LocalToUTC  
 Appelez cette méthode pour convertir une heure de fichier local à une heure de fichier basée sur le temps universel coordonné (UTC).  
  
```
CFileTime LocalToUTC() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un `CFileTime` objet contenant l’heure au format UTC.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CFileTime::UTCToLocal](#utctolocal).  
  
##  <a name="a-namemilliseconda--cfiletimemillisecond"></a><a name="millisecond"></a>CFileTime::Millisecond  
 Une donnée membre static stocker le nombre d’intervalles de 100 nanosecondes qui composent une milliseconde.  
  
```
static const ULONGLONG Millisecond = 10000;
```  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCFiles&#44;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]  
  
##  <a name="a-nameminutea--cfiletimeminute"></a><a name="minute"></a>CFileTime::Minute  
 Une donnée membre static stocker le nombre d’intervalles de 100 nanosecondes qui composent une minute.  
  
```
static const ULONGLONG Minute = Second* 60;
```  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CFileTime::Millisecond](#millisecond).  
  
##  <a name="a-nameoperator-a--cfiletimeoperator--"></a><a name="operator_-"></a>CFileTime::operator-  
 Cet opérateur est utilisé pour exécuter la soustraction sur un `CFileTime` ou `CFileTimeSpan` objet.  
  
```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan`.  
  
 `ft`  
 Objet `CFileTime`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un `CFileTime` objet ou un `CFileTimeSpan` objet représentant le résultat de la différence de temps entre les deux objets.  
  
##  <a name="a-nameoperatorneqa--cfiletimeoperator-"></a><a name="operator_neq"></a>CFileTime::operator ! =  
 Cet opérateur compare deux `CFileTime` objets sont inégaux.  
  
```
bool operator!=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `ft`  
 Objet `CFileTime` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si l’élément en cours de comparaison n’est pas égale à la `CFileTime` objet **false**.  
  
##  <a name="a-nameoperatoradda--cfiletimeoperator-"></a><a name="operator_add"></a>CFileTime::operator +  
 Cet opérateur permet d'effectuer une addition sur un objet `CFileTimeSpan`.  
  
```
CFileTime operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un `CFileTime` objet représentant le résultat de l’heure d’origine plus une heure relative.  
  
##  <a name="a-nameoperatoraddeqa--cfiletimeoperator-"></a><a name="operator_add_eq"></a>CFileTime::operator +=  
 Cet opérateur permet d'effectuer une addition sur un objet `CFileTimeSpan` et d'assigner le résultat à l'objet actuel.  
  
```
CFileTime& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Objet `CFileTimeSpan`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la mise à jour `CFileTime` objet représentant le résultat de l’heure d’origine plus une heure relative.  
  
##  <a name="a-nameoperatorlta--cfiletimeoperator-lt"></a><a name="operator_lt"></a>CFileTime::operator&lt;  
 Cet opérateur compare deux objets `CFileTime` pour déterminer le plus petit.  
  
```
bool operator<(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `ft`  
 Objet `CFileTime` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si le premier objet est inférieure (précédemment en temps) à la seconde, **false** dans le cas contraire.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCFiles&#43;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]  
  
##  <a name="a-nameoperatorlteqa--cfiletimeoperator-lt"></a><a name="operator_lt_eq"></a>CFileTime::operator&lt;=  
 Cet opérateur compare deux objets `CFileTime` pour déterminer le plus petit ou leur égalité.  
  
```
bool operator<=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `ft`  
 Objet `CFileTime` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si le premier objet est inférieur à (antérieur dans le temps) ou égale à la seconde, sinon **false**.  
  
##  <a name="a-nameoperatoreqa--cfiletimeoperator-"></a><a name="operator_eq"></a>CFileTime::operator =  
 L’opérateur d’assignation.  
  
```
CFileTime& operator=(const FILETIME& ft) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `ft`  
 Un `CFileTime` objet contenant la date et l’heure.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la mise à jour `CFileTime` objet.  
  
##  <a name="a-nameoperator-eqa--cfiletimeoperator--"></a><a name="operator_-_eq"></a>CFileTime::operator =  
 Cet opérateur est utilisé pour exécuter la soustraction sur un `CFileTimeSpan` de l’objet et assigner le résultat à l’objet actuel.  
  
```
CFileTime& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Un `CFileTimeSpan` objet contenant l’heure relative à soustraire.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la mise à jour `CFileTime` objet.  
  
##  <a name="a-nameoperatoreqeqa--cfiletimeoperator-"></a><a name="operator_eq_eq"></a>CFileTime::operator ==  
 Cet opérateur compare deux objets `CFileTime` pour déterminer leur égalité.  
  
```
bool operator==(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `ft`  
 Le `CFileTime` objet à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si les objets sont égaux, sinon **false**.  
  
##  <a name="a-nameoperatorgta--cfiletimeoperator-gt"></a><a name="operator_gt"></a>CFileTime::operator&gt;  
 Cet opérateur compare deux objets `CFileTime` pour déterminer le plus grand.  
  
```
bool operator>(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `ft`  
 Objet `CFileTime` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si le premier objet est supérieur à (plus loin dans le temps) que le second, sinon **false**.  
  
##  <a name="a-nameoperatorgteqa--cfiletimeoperator-gt"></a><a name="operator_gt_eq"></a>CFileTime::operator&gt;=  
 Cet opérateur compare deux objets `CFileTime` pour déterminer le plus grand ou leur égalité.  
  
```
bool operator>=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `ft`  
 Objet `CFileTime` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si le premier objet est supérieur à (plus loin dans le temps) ou égale à la seconde, sinon **false**.  
  
##  <a name="a-nameseconda--cfiletimesecond"></a><a name="second"></a>CFileTime::Second  
 Une donnée membre static stocker le nombre d’intervalles de 100 nanosecondes qui constituent un jour.  
  
```
static const ULONGLONG Second = Millisecond* 1000;
```  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CFileTime::Millisecond](#millisecond).  
  
##  <a name="a-namesettimea--cfiletimesettime"></a><a name="settime"></a>CFileTime::SetTime  
 Appelez cette méthode pour définir la date et l’heure stockée par le `CFileTime` objet.  
  
```
void SetTime(ULONGLONG nTime) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nTime`  
 La valeur de 64 bits qui représente la date et l’heure, au format de temps universel coordonné (UTC) ou local.  
  
##  <a name="a-nameutctolocala--cfiletimeutctolocal"></a><a name="utctolocal"></a>CFileTime::UTCToLocal  
 Appelez cette méthode pour convertir l’heure basée sur le temps universel coordonné (UTC) heure de fichier local.  
  
```
CFileTime UTCToLocal() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un `CFileTime` objet contenant l’heure au format d’heure de fichier local.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCFiles&#42;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]  
  
##  <a name="a-nameweeka--cfiletimeweek"></a><a name="week"></a>CFileTime::Week  
 Une donnée membre static stocker le nombre d’intervalles de 100 nanosecondes qui composent une semaine.  
  
```
static const ULONGLONG Week = Day* 7;
```  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CFileTime::Millisecond](#millisecond).  
  
## <a name="see-also"></a>Voir aussi  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTimeSpan (classe)](../../atl-mfc-shared/reference/cfiletimespan-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [ATL et MFC des Classes partagées](../../atl-mfc-shared/atl-mfc-shared-classes.md)



