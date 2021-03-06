---
title: Classe CTimeSpan | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd95d26dd2df41f16091379c892f67319c218cc4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ctimespan-class"></a>Classe CTimeSpan
Un intervalle de temps, ce qui est stocké en interne en tant que le nombre de secondes dans l’intervalle de temps.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CTimeSpan
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CTimeSpan::CTimeSpan](#ctimespan)|Construit `CTimeSpan` objets de différentes manières.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CTimeSpan::Format](#format)|Convertit un `CTimeSpan` dans une chaîne mise en forme.|  
|[CTimeSpan::GetDays](#getdays)|Retourne une valeur qui représente le nombre de jours complètes dans ce `CTimeSpan`.|  
|[CTimeSpan::GetHours](#gethours)|Retourne une valeur qui représente le nombre d’heures le jour actuel (-23 et 23).|  
|[CTimeSpan::GetMinutes](#getminutes)|Retourne une valeur qui représente le nombre de minutes à l’heure actuelle (entre-59 et 59).|  
|[CTimeSpan::GetSeconds](#getseconds)|Retourne une valeur qui représente le nombre de secondes dans la minute actuelle (entre-59 et 59).|  
|[CTimeSpan::GetTimeSpan](#gettimespan)|Retourne la valeur de la `CTimeSpan` objet.|  
|[CTimeSpan::GetTotalHours](#gettotalhours)|Retourne une valeur qui représente le nombre total d’heures complètes dans ce `CTimeSpan`.|  
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|Retourne une valeur qui représente le nombre total de minutes complètes dans ce `CTimeSpan`.|  
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|Retourne une valeur qui représente le nombre total de secondes complètes dans ce `CTimeSpan`.|  
|[CTimeSpan::Serialize64](#serialize64)|Sérialise les données vers ou à partir d’une archive.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[opérateur + -](#operator_add_-)|Ajoute et soustrait `CTimeSpan` objets.|  
|[opérateur += =](#operator_add_eq_-_eq)|Ajoute et soustrait un `CTimeSpan` objet vers et à partir de ce `CTimeSpan`.|  
|[opérateur == < etc..](#ctimespan_comparison_operators)|Compare deux valeurs d’heure relative.|  
  
## <a name="remarks"></a>Notes  
 `CTimeSpan` ne dispose pas d’une classe de base.  
  
 `CTimeSpan` fonctions convertissent les secondes à différentes combinaisons de jours, heures, minutes et secondes.  
  
 Le `CTimeSpan` objet est stocké dans un **__time64_t** structure, ce qui est de 8 octets.  
  
 Une classe auxiliaire, [CTime](../../atl-mfc-shared/reference/ctime-class.md), représente une heure absolue.  
  
 Le `CTime` et `CTimeSpan` classes ne sont pas conçues pour la dérivation. Étant donné qu’aucune fonction virtuelle, la taille des deux `CTime` et `CTimeSpan` objets est exactement de 8 octets. La plupart des fonctions membres sont en ligne.  
  
 Pour plus d’informations sur l’utilisation de `CTimeSpan`, consultez les articles [Date et heure](../../atl-mfc-shared/date-and-time.md), et [gestion du temps](../../c-runtime-library/time-management.md) dans les *Run-Time Library Reference*.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atltime.h  
  
##  <a name="ctimespan_comparison_operators"></a>  Opérateurs de comparaison de CTimeSpan  
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
 [!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]  
  
##  <a name="ctimespan"></a>  CTimeSpan::CTimeSpan  
 Construit `CTimeSpan` objets de différentes manières.  
  
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
 A `CTimeSpan` objet qui existe déjà.  
  
 `time`  
 A **__time64_t** valeur d’heure, qui est le nombre de secondes dans l’intervalle de temps.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Jours, heures, minutes et secondes, respectivement.  
  
### <a name="remarks"></a>Notes  
 Tous ces constructeurs créent un nouveau `CTimeSpan` objet initialisé avec l’heure relative spécifiée. Chaque constructeur est décrit ci-dessous :  
  
- **(De CTimeSpan) ;**  Construit non initialisé `CTimeSpan` objet.  
  
- **CTimeSpan (CTimeSpan const &) ;**  Construit un `CTimeSpan` objet à partir d’un autre `CTimeSpan` valeur.  
  
- **CTimeSpan (__time64_t) ;**  Construit un `CTimeSpan` de l’objet d’un **__time64_t** type.  
  
- **CTimeSpan (LONG**, **int, int, int) ;** Construit un `CTimeSpan` objet à partir des composants avec chaque composant de la contrainte pour les plages suivantes :  
  
    |Composant|Plage|  
    |---------------|-----------|  
    |`lDays`|0-25 000 (environ)|  
    |`nHours`|0-23|  
    |`nMins`|0-59|  
    |`nSecs`|0-59|  
  
 Notez que la version Debug de la bibliothèque Microsoft Foundation Class déclare si un ou plusieurs des composants heure est hors limites. Il vous incombe de valider les arguments avant d’appeler.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]  
  
##  <a name="format"></a>  CTimeSpan::Format  
 Génère une chaîne mise en forme qui correspond à cet `CTimeSpan`.  
  
```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `pFormat`, `pszFormat`  
 Une mise en forme de chaîne similaire à la `printf` mise en forme de chaîne. Mise en forme de codes, précédés d’un pourcentage ( `%`) se connecter, sont remplacés par le correspondant `CTimeSpan` composant. Autres caractères dans la chaîne de mise en forme sont copiés sans modification à la chaîne retournée. La valeur et la signification des codes de mise en forme pour **Format** sont répertoriées ci-dessous :  
  
- **%D** nombre total de jours dans cette `CTimeSpan`  
  
- **%H** heures le jour actuel  
  
- **%M** minutes à l’heure actuelle  
  
- **%S** secondes dans la minute en cours  
  
- **%%** Symbole de pourcentage  
  
 `nID`  
 L’ID de la chaîne qui identifie ce format.  
  
### <a name="return-value"></a>Valeur de retour  
 A `CString` objet qui contient l’heure de mise en forme.  
  
### <a name="remarks"></a>Notes  
 La version Debug de la bibliothèque vérifie les codes de mise en forme et indique si le code n’est pas dans la liste ci-dessus.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]  
  
##  <a name="getdays"></a>  CTimeSpan::GetDays  
 Retourne une valeur qui représente le nombre de jours complètes dans ce `CTimeSpan`.  
  
```
LONGLONG GetDays() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de jours de 24 heures complètes dans l’intervalle de temps. Cette valeur peut être négative si l’intervalle de temps est un nombre négatif.  
  
### <a name="remarks"></a>Notes  
 Notez que l’heure d’été peut provoquer `GetDays` pour retourner un résultat potentiellement étonnant. Par exemple, lorsque l’heure d’été est en vigueur, **GetDays** indique le nombre de jours entre le 1er avril et le 1er mai comme 29, 30 pas, car un jour d’avril est réduit en une heure et par conséquent ne compte pas comme une journée complète.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]  
  
##  <a name="gethours"></a>  CTimeSpan::GetHours  
 Retourne une valeur qui représente le nombre d’heures le jour actuel (-23 et 23).  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre d’heures le jour actuel. La plage est comprise entre -23 et 23.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]  
  
##  <a name="getminutes"></a>  CTimeSpan::GetMinutes  
 Retourne une valeur qui représente le nombre de minutes à l’heure actuelle (entre-59 et 59).  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de minutes à l’heure actuelle. La plage est comprise entre -59 et 59.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetHours](#gethours).  
  
##  <a name="getseconds"></a>  CTimeSpan::GetSeconds  
 Retourne une valeur qui représente le nombre de secondes dans la minute actuelle (entre-59 et 59).  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de secondes dans la minute en cours. La plage est comprise entre -59 et 59.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetHours](#gethours).  
  
##  <a name="gettimespan"></a>  CTimeSpan::GetTimeSpan  
 Retourne la valeur de la `CTimeSpan` objet.  
  
```
__ time64_t GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur actuelle de la `CTimeSpan` objet.  
  
##  <a name="gettotalhours"></a>  CTimeSpan::GetTotalHours  
 Retourne une valeur qui représente le nombre total d’heures complètes dans ce `CTimeSpan`.  
  
```
LONGLONG GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre total d’heures complètes dans ce `CTimeSpan`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]  
  
##  <a name="gettotalminutes"></a>  CTimeSpan::GetTotalMinutes  
 Retourne une valeur qui représente le nombre total de minutes complètes dans ce `CTimeSpan`.  
  
```
LONGLONG GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre total de minutes complètes dans ce `CTimeSpan`.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetTotalHours](#gettotalhours).  
  
##  <a name="gettotalseconds"></a>  CTimeSpan::GetTotalSeconds  
 Retourne une valeur qui représente le nombre total de secondes complètes dans ce `CTimeSpan`.  
  
```
LONGLONG GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre total de secondes complètes dans ce `CTimeSpan`.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetTotalHours](#gettotalhours).  
  
##  <a name="operator_add_-"></a>  CTimeSpan::operator +, -  
 Ajoute et soustrait `CTimeSpan` objets.  
  
```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 La valeur à ajouter à la `CTimeSpan` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 A `CTimeSpan` objet représentant le résultat de l’opération.  
  
### <a name="remarks"></a>Notes  
 Ces deux opérateurs permettent d’ajouter ou soustraire `CTimeSpan` objets vers et depuis les uns des autres.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>  CTimeSpan::operator +=-=  
 Ajoute et soustrait un `CTimeSpan` objet vers et à partir de ce `CTimeSpan`.  
  
```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 La valeur à ajouter à la `CTimeSpan` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 La mise à jour `CTimeSpan` objet.  
  
### <a name="remarks"></a>Notes  
 Ces opérateurs permettent d’ajouter ou soustraire un `CTimeSpan` objet vers et à partir de ce `CTimeSpan`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]  
  
##  <a name="serialize64"></a>  CTimeSpan::Serialize64  
  
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
 La mise à jour `CArchive` objet.  
  
## <a name="see-also"></a>Voir aussi  
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes de partagées ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)


