---
title: COleDateTimeSpan (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.COleDateTimeSpan
- COleDateTimeSpan
- ATL::COleDateTimeSpan
dev_langs:
- C++
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4091ca2c766d56d8398119413778af0a0405b8ab
ms.lasthandoff: 02/24/2017

---
# <a name="coledatetimespan-class"></a>COleDateTimeSpan (classe)
Représente une heure relative, un intervalle de temps.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class COleDateTimeSpan
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDateTimeSpan::COleDateTimeSpan](#coledatetimespan)|Construit un objet `COleDateTimeSpan`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDateTimeSpan::Format](#format)|Génère une représentation de chaîne mise en forme d’un `COleDateTimeSpan` objet.|  
|[COleDateTimeSpan::GetDays](#getdays)|Retourne la composante jour de l’étendue de cet `COleDateTimeSpan` représente l’objet.|  
|[COleDateTimeSpan::GetHours](#gethours)|Retourne la partie heure de l’étendue de cet `COleDateTimeSpan` représente l’objet.|  
|[COleDateTimeSpan::GetMinutes](#getminutes)|Retourne la partie minute de l’étendue de cet `COleDateTimeSpan` représente l’objet.|  
|[COleDateTimeSpan::GetSeconds](#getseconds)|Retourne la deuxième partie de l’étendue de cet `COleDateTimeSpan` représente l’objet.|  
|[COleDateTimeSpan::GetStatus](#getstatus)|Obtient l’état (validité) de ce `COleDateTimeSpan` objet.|  
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|Retourne le nombre de jours cet `COleDateTimeSpan` représente l’objet.|  
|[COleDateTimeSpan::GetTotalHours](#gettotalhours)|Retourne le nombre d’heures pendant lesquelles cet `COleDateTimeSpan` représente l’objet.|  
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|Retourne le nombre de minutes cet `COleDateTimeSpan` représente l’objet.|  
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|Retourne le nombre de secondes cet `COleDateTimeSpan` représente l’objet.|  
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|Définit la valeur de cette `COleDateTimeSpan` objet.|  
|[COleDateTimeSpan::SetStatus](#setstatus)|Définit l’état (validité) de ce `COleDateTimeSpan` objet.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|||  
|-|-|  
|[opérateur +, -](#operator_add_-)|Ajouter, soustraire et modifier la connexion pour `COleDateTimeSpan` valeurs.|  
|[opérateur +=, =](#operator_add_eq_-_eq)|Ajouter ou soustraire un `COleDateTimeSpan` valeur à partir de ce `COleDateTimeSpan` valeur.|  
|[opérateur =](#operator_eq)|Copie un `COleDateTimeSpan` valeur.|  
|[opérateur ==<,></,><>](#coledatetimespan_relational_operators)|Comparer deux `COleDateTimeSpan` valeurs.|  
|[double (opérateur)](#operator_double)|Convertit cet `COleDateTimeSpan` valeur un **double**.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDateTimeSpan::m_span](#m_span)|Contient sous-jacent **double** pour ce `COleDateTimeSpan` objet.|  
|[COleDateTimeSpan::m_status](#m_status)|Contient l’état de ce `COleDateTimeSpan` objet.|  
  
## <a name="remarks"></a>Remarques  
 `COleDateTimeSpan`n’a pas d’une classe de base.  
  
 Un `COleDateTimeSpan` conserve la durée en jours.  
  
 `COleDateTimeSpan`est utilisé avec sa classe compagnon [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md). `COleDateTime`encapsule la **DATE** type de données d’OLE automation. `COleDateTime`représente les valeurs d’heure absolue. Tous les `COleDateTime` impliquant des calculs `COleDateTimeSpan` valeurs. La relation entre ces classes est analogue à celui entre [CTime](../../atl-mfc-shared/reference/ctime-class.md) et [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Pour plus d’informations sur la `COleDateTime` et `COleDateTimeSpan` des classes, consultez l’article [Date et heure : prise en charge Automation](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** ATLComTime.h  
  
##  <a name="a-namecoledatetimespanrelationaloperatorsa--coledatetimespan-relational-operators"></a><a name="coledatetimespan_relational_operators"></a>Opérateurs relationnels COleDateTimeSpan  
 Opérateurs de comparaison.  
  
```
bool operator==(const COleDateTimeSpan& dateSpan) const throw();
bool operator!=(const COleDateTimeSpan& dateSpan) const throw();
bool operator<(const COleDateTimeSpan& dateSpan) const throw();
bool operator>(const COleDateTimeSpan& dateSpan) const throw();
bool operator<=(const COleDateTimeSpan& dateSpan) const throw();
bool operator>=(const COleDateTimeSpan& dateSpan) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *dateSpan*  
 `COleDateTimeSpan` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Ces opérateurs de comparer deux valeurs de date/heure-intervalle et retourner **true** si la condition est true ; sinon **false**.  
  
### <a name="remarks"></a>Remarques  
  
> [!NOTE]
>  Un ATLASSERT ; se produit si des opérandes ne sont pas valide.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#25;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#26;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]  
  
##  <a name="a-namecoledatetimespana--coledatetimespancoledatetimespan"></a><a name="coledatetimespan"></a>COleDateTimeSpan::COleDateTimeSpan  
 Construit un objet `COleDateTimeSpan`.  
  
```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `dblSpanSrc`  
 Le nombre de jours doit être copié dans le nouvel `COleDateTimeSpan` objet.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Indiquer les valeurs de jour et d’heure à copier dans le nouveau `COleDateTimeSpan` objet.  
  
### <a name="remarks"></a>Remarques  
 Toutes ces constructeurs créent `COleDateTimeSpan` objets initialisés à la valeur spécifiée. Une brève description de chacun de ces constructeurs ci-dessous :  
  
- **() COleDateTimeSpan** construit un `COleDateTimeSpan` objet initialisé à 0.  
  
- **COleDateTimeSpan (** `dblSpanSrc` **)** construit un `COleDateTimeSpan` objet à partir d’une valeur à virgule flottante.  
  
- **COleDateTimeSpan (** `lDays` **,** `nHours` **,** `nMins` **,** `nSecs` **)** construit un `COleDateTimeSpan` objet initialisé avec les valeurs numériques spécifiées.  
  
 L’état de la nouvelle `COleDateTimeSpan` a valide à l’objet.  
  
 Pour plus d’informations sur les limites de `COleDateTimeSpan` valeurs, consultez l’article [Date et heure : prise en charge Automation](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#14;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]  
  
##  <a name="a-nameformata--coledatetimespanformat"></a><a name="format"></a>COleDateTimeSpan::Format  
 Génère une représentation de chaîne mise en forme d’un `COleDateTimeSpan` objet.  
  
```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `pFormat`  
 Une mise en forme de chaîne similaire à la `printf` mise en forme de chaîne. Mise en forme des codes, précédés d’un pourcentage ( `%`) se connecter, sont remplacés par le correspondant `COleDateTimeSpan` composant. Autres caractères dans la chaîne mise en forme sont copiés inchangés à la chaîne retournée. La valeur et la signification des codes de mise en forme pour **Format** sont répertoriées ci-dessous :  
  
- **%H** heures du jour actuel  
  
- **%M** minutes à l’heure actuelle  
  
- **%S** secondes dans la minute en cours  
  
- **%%**Symbole de pourcentage  
  
 Les codes de format quatre répertoriés ci-dessus sont les codes de Format acceptera uniquement.  
  
-  
  
 `nID`  
 ID de ressource de la chaîne de format de contrôle.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CString` qui contient la valeur de date/heure-intervalle de mise en forme.  
  
### <a name="remarks"></a>Remarques  
 Appelez ces fonctions pour créer une représentation sous forme de mise en forme de la valeur de l’intervalle de temps. Si l’état de ce `COleDateTimeSpan` objet est null, la valeur de retour est une chaîne vide. Si l’état n’est pas valide, la chaîne de retour est spécifiée par la ressource de chaîne **IDS_INVALID_DATETIMESPAN**.  
  
 Une brève description des formulaires pour cette fonction suit :  
  
 **Format(** `pFormat` **)**  
 Cet écran met en forme la valeur à l’aide de la chaîne de format qui contient les codes de mise en forme spéciale qui sont précédés d’un signe de pourcentage (%), comme dans `printf`. La chaîne mise en forme est passée en tant que paramètre à la fonction.  
  
 **Format(** `nID` **)**  
 Cet écran met en forme la valeur à l’aide de la chaîne de format qui contient les codes de mise en forme spéciale qui sont précédés d’un signe de pourcentage (%), comme dans `printf`. La chaîne mise en forme est une ressource. L’ID de ressource de cette chaîne est passée comme paramètre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#15;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]  
  
##  <a name="a-namegetdaysa--coledatetimespangetdays"></a><a name="getdays"></a>COleDateTimeSpan::GetDays  
 Récupère la partie jour de cette valeur de date-période.  
  
```
LONG GetDays() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La partie jour de cette valeur de date-période.  
  
### <a name="remarks"></a>Notes  
 La valeur de retour des valeurs de cette plage de fonction entre environ – 3,615,000 et 3,615,000.  
  
 Pour les autres fonctions interroger la valeur d’un `COleDateTimeSpan` d’objets, consultez les fonctions membres suivantes :  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#16;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]  
  
##  <a name="a-namegethoursa--coledatetimespangethours"></a><a name="gethours"></a>COleDateTimeSpan::GetHours  
 Récupère la partie de cette valeur de période date/heure.  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Les heures de cette valeur de date-période.  
  
### <a name="remarks"></a>Remarques  
 Les valeurs de retour de cette plage de fonction entre-23 et 23.  
  
 Pour les autres fonctions interroger la valeur d’un `COleDateTimeSpan` d’objets, consultez les fonctions membres suivantes :  
  
- [GetDays](#getdays)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#17;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]  
  
##  <a name="a-namegetminutesa--coledatetimespangetminutes"></a><a name="getminutes"></a>COleDateTimeSpan::GetMinutes  
 Récupère la partie minute de cette valeur de date-période.  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La partie minutes de cette valeur de date-période.  
  
### <a name="remarks"></a>Remarques  
 Les valeurs de retour de cette plage de fonction entre-59 et 59.  
  
 Pour les autres fonctions interroger la valeur d’un `COleDateTimeSpan` d’objets, consultez les fonctions membres suivantes :  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#18;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]  
  
##  <a name="a-namegetsecondsa--coledatetimespangetseconds"></a><a name="getseconds"></a>COleDateTimeSpan::GetSeconds  
 Récupère la deuxième partie de cette valeur de date-période.  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La partie secondes de cette valeur de date-période.  
  
### <a name="remarks"></a>Notes  
 Les valeurs de retour de cette plage de fonction entre-59 et 59.  
  
 Pour les autres fonctions interroger la valeur d’un `COleDateTimeSpan` d’objets, consultez les fonctions membres suivantes :  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities n °&19;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]  
  
##  <a name="a-namegetstatusa--coledatetimespangetstatus"></a><a name="getstatus"></a>COleDateTimeSpan::GetStatus  
 Obtient l’état (validité) de ce `COleDateTimeSpan` objet.  
  
```
DateTimeSpanStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’état de ce `COleDateTimeSpan` valeur.  
  
### <a name="remarks"></a>Notes  
 La valeur de retour est définie par le **DateTimeSpanStatus** type énuméré, qui est défini dans la `COleDateTimeSpan` classe.  
  
 `enum DateTimeSpanStatus{`  
  
 `valid = 0,`  
  
 `invalid = 1,`  
  
 `null = 2,`  
  
 `};`  
  
 Pour obtenir une brève description de ces valeurs d’état, consultez la liste suivante :  
  
- **COleDateTimeSpan::valid** indique que ce `COleDateTimeSpan` est valide.  
  
- **COleDateTimeSpan::invalid** indique que ce `COleDateTimeSpan` objet n’est pas valide ; autrement dit, sa valeur peut être incorrecte.  
  
- **COleDateTimeSpan::null** indique que ce `COleDateTimeSpan` objet est null, c'est-à-dire qu’aucune valeur n’a été fournie pour cet objet. (La valeur est « null » dans le sens de la base de données de « aucune valeur, les clauses having » plutôt que le C++ **NULL**.)  
  
 L’état d’un `COleDateTimeSpan` objet n’est pas valide dans les cas suivants :  
  
-   Si cet objet a rencontré un dépassement de capacité positif ou négatif lors d’une opération arithmétique d’attribution, à savoir, `+=` ou `-=`.  
  
-   Si une valeur non valide a été affectée à cet objet.  
  
-   Si l’état de cet objet a été explicitement défini non valide à l’aide de `SetStatus`.  
  
 Pour plus d’informations sur les opérations qui peuvent définir l’état à non valides, consultez la page [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) et [COleDateTimeSpan::operator +=, -=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).  
  
 Pour plus d’informations sur les limites de `COleDateTimeSpan` valeurs, consultez l’article [Date et heure : prise en charge Automation](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="a-namegettotaldaysa--coledatetimespangettotaldays"></a><a name="gettotaldays"></a>COleDateTimeSpan::GetTotalDays  
 Extrait cette valeur de date-durée exprimée en jours.  
  
```
double GetTotalDays() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Cette valeur de date-durée exprimée en jours. Bien que cette fonction est prototypée pour retourner une valeur double, elle retournera toujours une valeur entière.  
  
### <a name="remarks"></a>Notes  
 Les valeurs de retour de cette plage de fonction entre environ – 3.65e6 et 3.65e6.  
  
 Pour les autres fonctions interroger la valeur d’un `COleDateTimeSpan` d’objets, consultez les fonctions membres suivantes :  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#20;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]  
  
##  <a name="a-namegettotalhoursa--coledatetimespangettotalhours"></a><a name="gettotalhours"></a>COleDateTimeSpan::GetTotalHours  
 Extrait cette valeur de date-période exprimée en heures.  
  
```
double GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Cette valeur de date-période exprimée en heures. Bien que cette fonction est prototypée pour retourner une valeur double, elle retournera toujours une valeur entière.  
  
### <a name="remarks"></a>Remarques  
 Les valeurs de retour de cette plage de fonction entre environ – 8.77e7 et 8.77e7.  
  
 Pour les autres fonctions interroger la valeur d’un `COleDateTimeSpan` d’objets, consultez les fonctions membres suivantes :  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetTotalDays](#gettotaldays).  
  
##  <a name="a-namegettotalminutesa--coledatetimespangettotalminutes"></a><a name="gettotalminutes"></a>COleDateTimeSpan::GetTotalMinutes  
 Extrait cette valeur de date-durée exprimée en minutes.  
  
```
double GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Cette valeur de date-durée exprimée en minutes. Bien que cette fonction est prototypée pour retourner une valeur double, elle retournera toujours une valeur entière.  
  
### <a name="remarks"></a>Notes  
 Les valeurs de retour de cette plage de fonction entre environ – 5.26e9 et 5.26e9.  
  
 Pour les autres fonctions interroger la valeur d’un `COleDateTimeSpan` d’objets, consultez les fonctions membres suivantes :  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetTotalDays](#gettotaldays).  
  
##  <a name="a-namegettotalsecondsa--coledatetimespangettotalseconds"></a><a name="gettotalseconds"></a>COleDateTimeSpan::GetTotalSeconds  
 Extrait cette valeur de date/intervalle de temps exprimée en secondes.  
  
```
double GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Cette valeur de date/intervalle de temps exprimée en secondes. Bien que cette fonction est prototypée pour retourner une valeur double, elle retournera toujours une valeur entière.  
  
### <a name="remarks"></a>Notes  
 Les valeurs de retour de cette fonction est compris entre environ – 3.16e11 à 3.16e11.  
  
 Pour les autres fonctions interroger la valeur d’un `COleDateTimeSpan` d’objets, consultez les fonctions membres suivantes :  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetTotalDays](#gettotaldays).  
  
##  <a name="a-namemspana--coledatetimespanmspan"></a><a name="m_span"></a>COleDateTimeSpan::m_span  
 Sous-jacent **double** valeur `COleDateTime` objet.  
  
```
double m_span;
```  
  
### <a name="remarks"></a>Notes  
 Cette valeur exprime la date/période en jours.  
  
> [!CAUTION]
>  Modification de la valeur dans la **double** membre de données modifie la valeur de cette `COleDateTimeSpan` objet. Il ne modifie pas l’état de ce `COleDateTimeSpan` objet.  
  
##  <a name="a-namemstatusa--coledatetimespanmstatus"></a><a name="m_status"></a>COleDateTimeSpan::m_status  
 Le type de ce membre de données est le type énuméré **DateTimeSpanStatus**, qui est défini dans la `COleDateTimeSpan` classe.  
  
```
DateTimeSpanStatus m_status;
```  
  
### <a name="remarks"></a>Notes  
 `enum DateTimeSpanStatus{`  
  
 `valid = 0,`  
  
 `invalid = 1,`  
  
 `null = 2,`  
  
 `};`  
  
 Pour obtenir une brève description de ces valeurs d’état, consultez la liste suivante :  
  
- **COleDateTimeSpan::valid** indique que ce `COleDateTimeSpan` est valide.  
  
- **COleDateTimeSpan::invalid** indique que ce `COleDateTimeSpan` objet n’est pas valide ; autrement dit, sa valeur peut être incorrecte.  
  
- **COleDateTimeSpan::null** indique que ce `COleDateTimeSpan` objet est null, c'est-à-dire qu’aucune valeur n’a été fournie pour cet objet. (La valeur est « null » dans le sens de la base de données de « aucune valeur, les clauses having » plutôt que le C++ **NULL**.)  
  
 L’état d’un `COleDateTimeSpan` objet n’est pas valide dans les cas suivants :  
  
-   Si cet objet a rencontré un dépassement de capacité positif ou négatif lors d’une opération arithmétique d’attribution, à savoir, `+=` ou `-=`.  
  
-   Si une valeur non valide a été affectée à cet objet.  
  
-   Si l’état de cet objet a été explicitement défini non valide à l’aide de [SetStatus](#setstatus).  
  
 Pour plus d’informations sur les opérations qui peuvent définir l’état à non valides, consultez la page [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) et [COleDateTimeSpan::operator +=, -=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).  
  
> [!CAUTION]
>  Ce membre de données concerne les situations de programmation avancées. Vous devez utiliser les fonctions de membre inline [GetStatus](#getstatus) et [SetStatus](#setstatus). Consultez `SetStatus` pour des précautions supplémentaires concernant la définition explicite de ce membre de données.  
  
 Pour plus d’informations sur les limites de `COleDateTimeSpan` valeurs, consultez l’article [Date et heure : prise en charge Automation](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="a-nameoperatoreqa--coledatetimespanoperator-"></a><a name="operator_eq"></a>COleDateTimeSpan::operator =  
 Copie un `COleDateTimeSpan` valeur.  
  
```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```  
  
### <a name="remarks"></a>Remarques  
 Cet opérateur d’assignation surchargés copie la valeur de date/heure-plage source dans ce `COleDateTimeSpan` objet.  
  
##  <a name="a-nameoperatoradd-a--coledatetimespanoperator---"></a><a name="operator_add_-"></a>COleDateTimeSpan::operator +, -  
 Ajouter, soustraire et modifier la connexion pour `COleDateTimeSpan` valeurs.  
  
```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```  
  
### <a name="remarks"></a>Remarques  
 Les deux premiers opérateurs vous permettent d’ajouter et de soustraire les valeurs date-période. Le troisième vous permet de modifier le signe d’une valeur date-période.  
  
 Si un des opérandes est null, l’état de la `COleDateTimeSpan` la valeur est null.  
  
 Si un des opérandes n’est pas valide et que l’autre n’est pas null, l’état de la `COleDateTimeSpan` valeur n’est pas valide.  
  
 Pour plus d’informations sur les valeurs d’état valide, null et non valides, consultez la [m_status](#m_status) variable membre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities n °&23;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]  
  
##  <a name="a-nameoperatoraddeq-eqa--coledatetimespanoperator---"></a><a name="operator_add_eq_-_eq"></a>COleDateTimeSpan::operator +=, =  
 Ajouter ou soustraire un `COleDateTimeSpan` valeur à partir de ce `COleDateTimeSpan` valeur.  
  
```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>Notes  
 Ces opérateurs vous permettent d’ajouter et de soustraire les valeurs de date/heure-étendue à partir de ce `COleDateTimeSpan` objet. Si un des opérandes est null, l’état de la `COleDateTimeSpan` la valeur est null.  
  
 Si un des opérandes n’est pas valide et que l’autre n’est pas null, l’état de la `COleDateTimeSpan` valeur n’est pas valide.  
  
 Pour plus d’informations sur les valeurs d’état valide, null et non valides, consultez la [m_status](#m_status) variable membre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#24;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]  
  
##  <a name="a-nameoperatordoublea--coledatetimespanoperator-double"></a><a name="operator_double"></a>COleDateTimeSpan::operator double  
 Convertit cet `COleDateTimeSpan` valeur un **double**.  
  
```
operator double() const throw();
```  
  
### <a name="remarks"></a>Remarques  
 Cet opérateur retourne la valeur de cette `COleDateTimeSpan` valeur comme un nombre à virgule flottante de jours.  
  
##  <a name="a-namesetdatetimespana--coledatetimespansetdatetimespan"></a><a name="setdatetimespan"></a>COleDateTimeSpan::SetDateTimeSpan  
 Définit la valeur de cette valeur de date-période.  
  
```
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Indiquer les valeurs d’intervalle de date et d’intervalle de temps à copier dans cette `COleDateTimeSpan` objet.  
  
### <a name="remarks"></a>Notes  
 Pour les fonctions interroger la valeur d’un `COleDateTimeSpan` d’objets, consultez les fonctions membres suivantes :  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities n °&21;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]  
  
##  <a name="a-namesetstatusa--coledatetimespansetstatus"></a><a name="setstatus"></a>COleDateTimeSpan::SetStatus  
 Définit l’état (validité) de ce `COleDateTimeSpan` objet.  
  
```
void SetStatus(DateTimeSpanStatus status) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *status*  
 La nouvelle valeur pour ce `COleDateTimeSpan` objet.  
  
### <a name="remarks"></a>Remarques  
 Le *état* la valeur du paramètre est définie par le **DateTimeSpanStatus** type énuméré, qui est défini dans la `COleDateTimeSpan` classe.  
  
 `enum DateTimeSpanStatus{`  
  
 `valid = 0,`  
  
 `invalid = 1,`  
  
 `null = 2,`  
  
 `};`  
  
 Pour obtenir une brève description de ces valeurs d’état, consultez la liste suivante :  
  
- **COleDateTimeSpan::valid** indique que ce `COleDateTimeSpan` est valide.  
  
- **COleDateTimeSpan::invalid** indique que ce `COleDateTimeSpan` objet n’est pas valide ; autrement dit, sa valeur peut être incorrecte.  
  
- **COleDateTimeSpan::null** indique que ce `COleDateTimeSpan` objet est null, c'est-à-dire qu’aucune valeur n’a été fournie pour cet objet. (La valeur est « null » dans le sens de la base de données de « aucune valeur, les clauses having » plutôt que le C++ **NULL**.)  
  
    > [!CAUTION]
    >  Cette fonction concerne les situations de programmation avancées. Cette fonction ne modifie pas les données dans cet objet. Plus souvent il servira à définir l’état sur `null` ou **non valide**. Notez que l’opérateur d’assignation ( [opérateur =](#eq)) et [SetDateTimeSpan](#setdatetimespan) ne définissez pas l’état de l’objet en fonction de la valeur (s) source.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#22;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [COleDateTime (classe)](../../atl-mfc-shared/reference/coledatetime-class.md)   
 [CTime (classe)](../../atl-mfc-shared/reference/ctime-class.md)   
 [Classe CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [ATL et MFC des Classes partagées](../../atl-mfc-shared/atl-mfc-shared-classes.md)



