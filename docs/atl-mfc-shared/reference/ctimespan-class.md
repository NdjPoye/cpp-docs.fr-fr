---
title: Classe CTimeSpan | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CTimeSpan
- CTimeSpan
- timespan
- ATL::CTimeSpan
dev_langs:
- C++
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
caps.latest.revision: 17
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
ms.openlocfilehash: 5c76411f6c1302d406b07cc79d9c544e3ad8c43b
ms.lasthandoff: 02/24/2017

---
# <a name="ctimespan-class"></a>Classe CTimeSpan
Un intervalle de temps, qui est stocké en interne en tant que le nombre de secondes dans l’intervalle de temps.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CTimeSpan
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CTimeSpan::CTimeSpan](#ctimespan)|Constructions `CTimeSpan` objets de diverses façons.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CTimeSpan::Format](#format)|Convertit un `CTimeSpan` dans une chaîne mise en forme.|  
|[CTimeSpan::GetDays](#getdays)|Retourne une valeur qui représente le nombre de jours terminées dans ce `CTimeSpan`.|  
|[CTimeSpan::GetHours](#gethours)|Retourne une valeur qui représente le nombre d’heures dans la journée en cours (–23 à 23).|  
|[CTimeSpan::GetMinutes](#getminutes)|Retourne une valeur qui représente le nombre de minutes à l’heure actuelle (–59 à 59).|  
|[CTimeSpan::GetSeconds](#getseconds)|Retourne une valeur qui représente le nombre de secondes de la minute actuelle (–59 à 59).|  
|[CTimeSpan::GetTimeSpan](#gettimespan)|Retourne la valeur de la `CTimeSpan` objet.|  
|[CTimeSpan::GetTotalHours](#gettotalhours)|Retourne une valeur qui représente le nombre total d’heures terminées dans ce `CTimeSpan`.|  
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|Retourne une valeur qui représente le nombre total de minutes complètes dans ce `CTimeSpan`.|  
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|Retourne une valeur qui représente le nombre total de secondes complètes dans ce `CTimeSpan`.|  
|[CTimeSpan::Serialize64](#serialize64)|Sérialise des données vers ou à partir d’une archive.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[opérateur + :](#operator_add_-)|Ajoute, soustrait `CTimeSpan` objets.|  
|[opérateur += – =](#operator_add_eq_-_eq)|Ajoute, soustrait un `CTimeSpan` objet vers et à partir de ce `CTimeSpan`.|  
|[opérateur ==<>](#ctimespan_comparison_operators)|Compare deux valeurs d’heure relative.|  
  
## <a name="remarks"></a>Notes  
 `CTimeSpan`n’a pas d’une classe de base.  
  
 `CTimeSpan`fonctions convertissent les secondes à différentes combinaisons de jours, heures, minutes et secondes.  
  
 Le `CTimeSpan` objet est stocké dans un **__time64_t** structure, qui est de 8 octets.  
  
 Une classe Compagnon, [CTime](../../atl-mfc-shared/reference/ctime-class.md), représente une heure absolue.  
  
 Le `CTime` et `CTimeSpan` ne sont pas conçus pour la dérivation de classes. Étant donné qu’aucune fonction virtuelle, la taille des deux `CTime` et `CTimeSpan` objets correspond exactement à 8 octets. La plupart des fonctions membres sont en ligne.  
  
 Pour plus d’informations sur l’utilisation de `CTimeSpan`, consultez les articles [Date et heure](../../atl-mfc-shared/date-and-time.md), et [gestion du temps](../../c-runtime-library/time-management.md) dans les *Run-Time Library Reference*.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atltime.h  
  
##  <a name="a-namectimespancomparisonoperatorsa--ctimespan-comparison-operators"></a><a name="ctimespan_comparison_operators"></a>Opérateurs de comparaison de CTimeSpan  
 Opérateurs de comparaison.  
  
```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
  
 Objet à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Ces opérateurs comparent deux valeurs d’heure relative. Elles retournent **true** si la condition est true ; sinon **false**.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#169;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]  
  
##  <a name="a-namectimespana--ctimespanctimespan"></a><a name="ctimespan"></a>CTimeSpan::CTimeSpan  
 Constructions `CTimeSpan` objets de diverses façons.  
  
```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(  
 LONG lDays,
 int nHours,
 int nMins,
 int nSecs) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *timeSpanSrc*  
 Un `CTimeSpan` objet qui existe déjà.  
  
 `time`  
 A **__time64_t** valeur d’heure, qui est le nombre de secondes dans l’intervalle de temps. Dans les versions de Visual C++ 6.0 et versions antérieures, `time` a une valeur de `time_t`. Visual C++ .NET ou version ultérieure en mode silencieux convertit un `time_t` paramètre **__time64_t**.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Jours, heures, minutes et secondes, respectivement.  
  
### <a name="remarks"></a>Remarques  
 Tous ces constructeurs créent un nouveau `CTimeSpan` objet initialisé avec l’heure relative spécifiée. Chaque constructeur est décrit ci-dessous :  
  
- **() CTimeSpan ; ** Construit non initialisé `CTimeSpan` objet.  
  
- **CTimeSpan (const CTimeSpan se); ** Construit un `CTimeSpan` objet à partir d’un autre `CTimeSpan` valeur.  
  
- **CTimeSpan (__time64_t) ; ** Construit un `CTimeSpan` de l’objet d’une **__time64_t** type.  
  
- **CTimeSpan (LONG**, **int, int, int) ;** Construit un `CTimeSpan` objet à partir de composants chaque composant limitées pour les plages suivantes :  
  
    |Composant|Range|  
    |---------------|-----------|  
    |`lDays`|0 –&25;&000; (environ)|  
    |`nHours`|0–23|  
    |`nMins`|0–59|  
    |`nSecs`|0–59|  
  
 Notez que la version Debug de la bibliothèque Microsoft Foundation Class déclare si un ou plusieurs des composants heure est hors limites. Il vous incombe de valider les arguments avant l’appel.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#162;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]  
  
##  <a name="a-nameformata--ctimespanformat"></a><a name="format"></a>CTimeSpan::Format  
 Génère une chaîne mise en forme qui correspond à ce `CTimeSpan`.  
  
```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `pFormat`, `pszFormat`  
 Une mise en forme de chaîne similaire à la `printf` mise en forme de chaîne. Mise en forme des codes, précédés d’un pourcentage ( `%`) se connecter, sont remplacés par le correspondant `CTimeSpan` composant. Autres caractères dans la chaîne mise en forme sont copiés inchangés à la chaîne retournée. La valeur et la signification des codes de mise en forme pour **Format** sont répertoriées ci-dessous :  
  
- **%D** nombre total de jours dans ce`CTimeSpan`  
  
- **%H** heures du jour actuel  
  
- **%M** minutes à l’heure actuelle  
  
- **%S** secondes dans la minute en cours  
  
- **%%**Symbole de pourcentage  
  
 `nID`  
 ID de la chaîne qui identifie ce format.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CString` objet qui contient l’heure de mise en forme.  
  
### <a name="remarks"></a>Remarques  
 La version Debug de la bibliothèque vérifie les codes de mise en forme et indique si le code n’est pas dans la liste ci-dessus.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#163;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]  
  
##  <a name="a-namegetdaysa--ctimespangetdays"></a><a name="getdays"></a>CTimeSpan::GetDays  
 Retourne une valeur qui représente le nombre de jours terminées dans ce `CTimeSpan`.  
  
```
LONGLONG GetDays() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de jours de 24 heures terminées dans l’intervalle de temps. Cette valeur peut être négative si l’intervalle de temps est négatif.  
  
### <a name="remarks"></a>Remarques  
 Notez que l’heure d’été peut provoquer `GetDays` pour renvoyer un résultat potentiellement surprenant. Par exemple, lorsque l’heure d’été est en vigueur, **GetDays** indique que le nombre de jours entre le 1er avril et mai 1 29, 30 pas, car un jour en avril est réduit à une heure et par conséquent n’est pas considéré comme un jour complet.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#164;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]  
  
##  <a name="a-namegethoursa--ctimespangethours"></a><a name="gethours"></a>CTimeSpan::GetHours  
 Retourne une valeur qui représente le nombre d’heures dans la journée en cours (–23 à 23).  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre d’heures du jour actuel. La plage est –23 et 23.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#165;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]  
  
##  <a name="a-namegetminutesa--ctimespangetminutes"></a><a name="getminutes"></a>CTimeSpan::GetMinutes  
 Retourne une valeur qui représente le nombre de minutes à l’heure actuelle (–59 à 59).  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de minutes à l’heure actuelle. La plage est –59 et 59.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetHours](#gethours).  
  
##  <a name="a-namegetsecondsa--ctimespangetseconds"></a><a name="getseconds"></a>CTimeSpan::GetSeconds  
 Retourne une valeur qui représente le nombre de secondes de la minute actuelle (–59 à 59).  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de secondes dans la minute en cours. La plage est –59 et 59.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetHours](#gethours).  
  
##  <a name="a-namegettimespana--ctimespangettimespan"></a><a name="gettimespan"></a>CTimeSpan::GetTimeSpan  
 Retourne la valeur de la `CTimeSpan` objet.  
  
```
__ time64_t GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur actuelle de la `CTimeSpan` objet.  
  
##  <a name="a-namegettotalhoursa--ctimespangettotalhours"></a><a name="gettotalhours"></a>CTimeSpan::GetTotalHours  
 Retourne une valeur qui représente le nombre total d’heures terminées dans ce `CTimeSpan`.  
  
```
LONGLONG GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre total d’heures terminées dans ce `CTimeSpan`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#166;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]  
  
##  <a name="a-namegettotalminutesa--ctimespangettotalminutes"></a><a name="gettotalminutes"></a>CTimeSpan::GetTotalMinutes  
 Retourne une valeur qui représente le nombre total de minutes complètes dans ce `CTimeSpan`.  
  
```
LONGLONG GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre total de minutes complètes dans ce `CTimeSpan`.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetTotalHours](#gettotalhours).  
  
##  <a name="a-namegettotalsecondsa--ctimespangettotalseconds"></a><a name="gettotalseconds"></a>CTimeSpan::GetTotalSeconds  
 Retourne une valeur qui représente le nombre total de secondes complètes dans ce `CTimeSpan`.  
  
```
LONGLONG GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre total de secondes complètes dans ce `CTimeSpan`.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetTotalHours](#gettotalhours).  
  
##  <a name="a-nameoperatoradd-a--ctimespanoperator---"></a><a name="operator_add_-"></a>CTimeSpan::operator +, -  
 Ajoute, soustrait `CTimeSpan` objets.  
  
```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 La valeur à ajouter à la `CTimeSpan` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CTimeSpan` objet représentant le résultat de l’opération.  
  
### <a name="remarks"></a>Notes  
 Ces deux opérateurs permettent d’ajouter et de soustraire `CTimeSpan` objets vers et à partir de l’autre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#167;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]  
  
##  <a name="a-nameoperatoraddeq-eqa--ctimespanoperator---"></a><a name="operator_add_eq_-_eq"></a>CTimeSpan::operator +=, =  
 Ajoute, soustrait un `CTimeSpan` objet vers et à partir de ce `CTimeSpan`.  
  
```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 La valeur à ajouter à la `CTimeSpan` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Mise à jour `CTimeSpan` objet.  
  
### <a name="remarks"></a>Remarques  
 Ces opérateurs permettent d’ajouter et de soustraire un `CTimeSpan` objet vers et à partir de ce `CTimeSpan`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#168;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]  
  
##  <a name="a-nameserialize64a--ctimespanserialize64"></a><a name="serialize64"></a>CTimeSpan::Serialize64  
  
> [!NOTE]
>  Cette méthode est uniquement disponible dans les projets MFC.  
  
 Sérialise les données associées à la variable membre vers ou à partir d’une archive.  
  
```
CArchive& Serialize64(CArchive& ar);
```  
  
### <a name="parameters"></a>Paramètres  
 `ar`  
 Le `CArchive` objet que vous souhaitez mettre à jour.  
  
### <a name="return-value"></a>Valeur de retour  
 Mise à jour `CArchive` objet.  
  
## <a name="see-also"></a>Voir aussi  
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [ATL et MFC des Classes partagées](../../atl-mfc-shared/atl-mfc-shared-classes.md)



