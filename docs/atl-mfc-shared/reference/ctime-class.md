---
title: Classe CTime | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CTime
- CTime
- ATL::CTime
dev_langs:
- C++
helpviewer_keywords:
- CTime class
- shared classes, CTime
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
caps.latest.revision: 30
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
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: 56b8b5c3574a7a53a4e259412b1b1326973bcac9
ms.lasthandoff: 02/28/2017

---
# <a name="ctime-class"></a>CTime (classe)
Représente une date et une heure absolue.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CTime  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CTime::CTime](#ctime)|Constructions `CTime` objets de diverses façons.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CTime::Format](#format)|Convertit un `CTime` un objet en une chaîne mise en forme, en fonction du fuseau horaire local.|  
|[CTime::FormatGmt](#formatgmt)|Convertit un `CTime` un objet en une chaîne mise en forme, en fonction de l’heure UTC.|  
|[CTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Convertit les informations de temps stockées dans le `CTime` objet à une structure Win32 compatibles DBTIMESTAMP.|  
|[CTime::GetAsSystemTime](#getassystemtime)|Convertit les informations de temps stockées dans les `CTime` objet Win32 compatibles [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) structure.|  
|[CTime::GetCurrentTime](#getcurrenttime)|Crée un `CTime` objet qui représente l’heure actuelle (la fonction membre statique).|  
|[CTime::GetDay](#getday)|Retourne la jour représenté par le `CTime` objet.|  
|[CTime::GetDayOfWeek](#getdayofweek)|Retourne le jour de la semaine représenté par le `CTime` objet.|  
|[CTime::GetGmtTm](#getgmttm)|Décompose un `CTime` objet en composants, en fonction de l’heure UTC.|  
|[CTime::GetHour](#gethour)|Retourne l’heure représentée par le `CTime` objet.|  
|[CTime::GetLocalTm](#getlocaltm)|Décompose un `CTime` objet en composants, selon le fuseau horaire local.|  
|[CTime::GetMinute](#getminute)|Retourne la minute représentée par le `CTime` objet.|  
|[CTime::GetMonth](#getmonth)|Retourne le mois représenté par le `CTime` objet.|  
|[CTime::GetSecond](#getsecond)|Retourne le second, représenté par le `CTime` objet.|  
|[CTime::GetTime](#gettime)|Retourne un **__time64_t** la valeur de la donnée `CTime` objet.|  
|[CTime::GetYear](#getyear)|Retourne l’année représentée par le `CTime` objet.|  
|[CTime::Serialize64](#serialize64)|Sérialise des données vers ou à partir d’une archive.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[opérateur + :](#operator_add_-)|Ces opérateurs ajouter ou soustraire `CTimeSpan` et `CTime` objets.|  
|[opérateur +=, =](#operator_add_eq_-_eq)|Ces opérateurs ajouter ou soustraire un `CTimeSpan` objet vers et depuis cette `CTime` objet.|  
|[opérateur =](#operator_eq)|L’opérateur d’assignation.|  
|[opérateur ==< ,="">](#ctime_comparison_operators)|Opérateurs de comparaison.|  
  
## <a name="remarks"></a>Notes  
 `CTime`n’a pas d’une classe de base.  
  
 `CTime`les valeurs sont basées sur le temps universel (UTC), qui est équivalent au temps universel (Greenwich Mean Time, GMT). Consultez la page [gestion du temps](../../c-runtime-library/time-management.md) pour plus d’informations sur la façon dont le fuseau horaire est déterminé.  
  
 Lorsque vous créez un `CTime` de l’objet, définissez les `nDST` paramètre 0 pour indiquer que l’heure standard est activée, ou à une valeur supérieure à 0 pour indiquer que l’heure d’été est en vigueur, ou à une valeur inférieure à zéro pour que le calcul de code de bibliothèque Runtime C si l’heure standard ou l’heure d’été est en vigueur. `tm_isdst` est un champ obligatoire. S’il est ne pas définie, sa valeur est indéfinie et la valeur de retour de [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) est imprévisible. Si `timeptr` pointe vers une structure tm retournée par un appel précédent à [asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), ou [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), le `tm_isdst` champ contient la valeur correcte.  
  
 Une classe Compagnon, [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), représente un intervalle de temps.  
  
 Le `CTime` et `CTimeSpan` ne sont pas conçus pour la dérivation de classes. Étant donné qu’aucune fonction virtuelle, la taille de `CTime` et `CTimeSpan` objets correspond exactement à 8 octets. La plupart des fonctions membres sont en ligne.  
  
> [!NOTE]
>  La limite de date supérieure est 12/31/3000. La limite inférieure est 1/1/1970 12:00:00 AM GMT.  
  
 Pour plus d’informations sur l’utilisation de `CTime`, consultez les articles [Date et heure](../../atl-mfc-shared/date-and-time.md), et [gestion du temps](../../c-runtime-library/time-management.md) dans la référence de la bibliothèque Runtime.  
  
> [!NOTE]
>  Le `CTime` structure a été remplacée par MFC 7.1 vers MFC 8.0. Si vous sérialisez un `CTime` structure à l’aide de la `operator <<` MFC 8.0 ou une version ultérieure, le fichier sera pas lisible sur les versions antérieures de MFC.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atltime.h  
  
##  <a name="a-namectimecomparisonoperatorsa--ctime-comparison-operators"></a><a name="ctime_comparison_operators"></a>Opérateurs de comparaison de CTime  
 Opérateurs de comparaison.  
  
```  
bool operator==(CTime time) const throw(); 
bool operator!=(CTime time) const throw();
bool operator<(CTime time) const throw();
bool operator>(CTime time) const throw();
bool operator<=(CTime time) const throw();
bool operator>=(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>Paramètres  
 `time`  
 Objet `CTime` à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Ces opérateurs comparent deux fois absolus et retournent **true** si la condition est true ; sinon **false**.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#161;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]  
  
##  <a name="a-namectimea--ctimectime"></a><a name="ctime"></a>CTime::CTime  
 Crée un objet `CTime` objet initialisé avec l’heure spécifiée.  
  
```  
CTime() throw(); 
CTime(__time64_t time) throw();
CTime(int nYear, int nMonth, int nDay,
      int nHour, int nMin, int nSec, int nDST = -1);
CTime(WORD wDosDate, WORD wDosTime, int nDST = -1);
CTime(const SYSTEMTIME& st, int nDST = - 1) throw();
CTime(const FILETIME& ft, int nDST = - 1);
CTime(const DBTIMESTAMP& dbts,int nDST = -1) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `timeSrc`  
 Indique un `CTime` objet qui existe déjà.  
  
 `time`  
 A **__time64_t** valeur d’heure, qui est le nombre de secondes après le 1er janvier 1970 UTC. Notez que cela soit ajustée à votre heure locale. Par exemple, si vous travaillez à New York et créez un `CTime` en passant un paramètre de 0, [CTime::GetMonth](#getmonth) retourne 12.  
  
 Dans les versions de Visual C++ 6.0 et versions antérieures, `time` a une valeur de `time_t`. Visual C++ .NET et versions ultérieures convertit un `time_t` paramètre **__time64_t**.  
  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 Indique les valeurs de date et d’heure à copier dans le nouveau `CTime` objet.  
  
 `nDST`  
 Indique si l’heure d’été est en vigueur. Peut avoir l’une des trois valeurs suivantes :  
  
- `nDST`valeur 0Standard temps est en vigueur.  
  
- `nDST`Attribuez une valeur supérieure à 0Daylight l’heure d’été est en vigueur.  
  
- `nDST`Affectez une valeur inférieure à la valeur par défaut 0The. Calcule automatiquement si l’heure standard ou l’heure d’été est en vigueur.  
  
 `wDosDate`, `wDosTime`  
 Valeurs de date et heure de MS-DOS pour être converti en une valeur date/heure et copiés dans le nouvel `CTime` objet.  
  
 `st`  
 A [SYSTEMTIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/d6609fff-1931-4818-8a26-f042630af0b0/locales/en-us) structure à être convertie en valeur de date/heure et copiés dans le nouvel `CTime` objet.  
  
 `ft`  
 A [FILETIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/979ce746-dc17-4147-89f8-41d05c5fcc5f/locales/en-us) structure à être convertie en valeur de date/heure et copiés dans le nouvel `CTime` objet.  
  
 @dbts  
 Une référence à une structure DBTIMESTAMP contenant l’heure locale actuelle.  
  
### <a name="remarks"></a>Notes  
 Chaque constructeur est décrit ci-dessous :  
  
- **CTime() ; ** Construit non initialisé `CTime` objet. Ce constructeur vous permet de définir `CTime` tableaux d’objet. Vous devez initialiser ces tableaux avec des heures valides avant de l’utiliser.  
  
- **CTime (const CTime se); ** Construit un `CTime` objet à partir d’un autre `CTime` valeur.  
  
- **CTime (__time64_t) ; ** Construit un `CTime` de l’objet d’une **__time64_t** type. Ce constructeur s’attend à une heure UTC et convertit le résultat à une heure locale avant de stocker le résultat.  
  
- **CTime (int, int,...) ; ** Construit un `CTime` objet à partir de composants heure locale chaque composant limitées pour les plages suivantes :  
  
    |Composant|Range|  
    |---------------|-----------|  
    |`nYear`|1970–3000|  
    |`nMonth`|1–12|  
    |`nDay`|1–31|  
    |`nHour`|0-23|  
    |`nMin`|0-59|  
    |`nSec`|0-59|  
  
     Ce constructeur effectue la conversion appropriée au format UTC. La version Debug de la bibliothèque Microsoft Foundation Class déclare si un ou plusieurs des composants heure sont hors limites. Vous devez valider les arguments avant l’appel. Ce constructeur s’attend à une heure locale.  
  
- **CTime (WORD, WORD) ; ** Construit un `CTime` objet à partir des valeurs de date et heure de MS-DOS spécifiés. Ce constructeur s’attend à une heure locale.  
  
- **CTime (const SYSTEMTIME se); ** Construit un `CTime` de l’objet d’un `SYSTEMTIME` structure. Ce constructeur s’attend à une heure locale.  
  
- **CTime (const FILETIME se); ** Construit un `CTime` de l’objet d’un `FILETIME` structure. Vous aurez probablement n’utilisez pas `CTime FILETIME` directement l’initialisation. Si vous utilisez un `CFile` objet pour manipuler un fichier, `CFile::GetStatus` récupère l’horodatage du fichier pour vous via un `CTime` objet initialisé avec un `FILETIME` structure. Ce constructeur suppose une heure UTC et convertit automatiquement la valeur en heure locale avant de stocker le résultat.  
  
    > [!NOTE]
    >  Le constructeur à l’aide de **DBTIMESTAMP** paramètre n’est disponible que lorsque OLEDB.h est inclus.  
  
 Pour plus d’informations, consultez la [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) et [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Consultez également la [MS-DOS Date et heure](http://msdn.microsoft.com/library/windows/desktop/ms724503) entrée dans le [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#148;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]  
  
##  <a name="a-nameformata--ctimeformat"></a><a name="format"></a>CTime::Format  
 Appelez cette fonction membre pour créer une représentation sous forme de mise en forme de la valeur de date et d’heure.  
  
```  
CString Format(LPCTSTR pszFormat) const; 
CString Format(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>Paramètres  
 `pszFormat`  
 Une mise en forme de chaîne similaire à la `printf` mise en forme de chaîne. Mise en forme des codes, précédés d’un pourcentage ( `%`) se connecter, sont remplacés par le correspondant `CTime` composant. Autres caractères dans la chaîne mise en forme sont copiés inchangés à la chaîne retournée. Consultez la fonction d’exécution [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) pour obtenir la liste de codes de mise en forme.  
  
 `nFormatID`  
 ID de la chaîne qui identifie ce format.  
  
### <a name="return-value"></a>Valeur de retour  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) qui contient l’heure de mise en forme.  
  
### <a name="remarks"></a>Remarques  
 Si l’état de ce `CTime` objet est null, la valeur de retour est une chaîne vide.  
  
 Cette méthode lève une exception si la valeur de date et d’heure à mettre en forme n’est pas compris entre le 1er janvier 1970 à 31 décembre 3000 à minuit heure universelle coordonnée (UTC).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#149;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]  
  
##  <a name="a-nameformatgmta--ctimeformatgmt"></a><a name="formatgmt"></a>CTime::FormatGmt  
 Génère une chaîne mise en forme qui correspond à ce `CTime` objet.  
  
```  
CString FormatGmt(LPCTSTR pszFormat) const; 
CString FormatGmt(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>Paramètres  
 `pszFormat`  
 Spécifie une chaîne mise en forme semblable à la `printf` mise en forme de chaîne. Consultez la fonction d’exécution [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) pour plus d’informations.  
  
 `nFormatID`  
 ID de la chaîne qui identifie ce format.  
  
### <a name="return-value"></a>Valeur de retour  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) qui contient l’heure de mise en forme.  
  
### <a name="remarks"></a>Remarques  
 La valeur d’heure n’est pas convertie et reflète donc UTC.  
  
 Cette méthode lève une exception si la valeur de date et d’heure à mettre en forme n’est pas compris entre le 1er janvier 1970 à 31 décembre 3000 à minuit heure universelle coordonnée (UTC).  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CTime::Format](#format).  
  
##  <a name="a-namegetasdbtimestampa--ctimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a>CTime::GetAsDBTIMESTAMP  
 Appelez cette fonction membre pour convertir les informations de temps stockées dans le `CTime` objet à une structure Win32 compatibles DBTIMESTAMP.  
  
```  
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `dbts`  
 Une référence à une structure DBTIMESTAMP contenant l’heure locale actuelle.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Stocke l'heure résultante dans la structure `dbts` référencée. Le **DBTIMESTAMP** structure de données initialisée par cette fonction aura son **fraction** membre défini à zéro.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#150;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]  
  
##  <a name="a-namegetassystemtimea--ctimegetassystemtime"></a><a name="getassystemtime"></a>CTime::GetAsSystemTime  
 Appelez cette fonction membre pour convertir les informations de temps stockées dans les `CTime` objet Win32 compatibles [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) structure.  
  
```  
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *timeDest*  
 Une référence à un [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) structure qui contiendra la valeur de date/heure convertie de la `CTime` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 True si l’opération a réussi ; Sinon, false.  
  
### <a name="remarks"></a>Remarques  
 `GetAsSystemTime`stocke l’heure résultante dans référencé *timeDest* structure. Le `SYSTEMTIME` structure de données initialisée par cette fonction aura son **wMilliseconds** membre défini à zéro.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#151;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]  
  
##  <a name="a-namegetcurrenttimea--ctimegetcurrenttime"></a><a name="getcurrenttime"></a>CTime::GetCurrentTime  
 Retourne un `CTime` objet qui représente l’heure actuelle.  
  
```  
static CTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Retourne la date système actuelle et l’heure en temps universel coordonné (UTC).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#152;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]  
  
##  <a name="a-namegetdaya--ctimegetday"></a><a name="getday"></a>CTime::GetDay  
 Retourne la jour représenté par le `CTime` objet.  
  
```  
int GetDay() const throw(); 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le jour du mois, en fonction de l’heure locale, dans la plage 1 à 31.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction appelle `GetLocalTm`, qui utilise une mémoire tampon interne, alloué de manière statique. Les données dans cette mémoire tampon sont remplacées en raison d’appels à d’autres `CTime` les fonctions membres.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#153;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]  
  
##  <a name="a-namegetdayofweeka--ctimegetdayofweek"></a><a name="getdayofweek"></a>CTime::GetDayOfWeek  
 Retourne le jour de la semaine représenté par le `CTime` objet.  
  
```  
int GetDayOfWeek() const throw(); 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le jour de la semaine en fonction de l’heure locale. 1 = dimanche, 2 = lundi, 7 = samedi.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction appelle `GetLocalTm`, qui utilise de manière statique interne tampon allouée. Les données dans cette mémoire tampon sont remplacées en raison d’appels à d’autres `CTime` les fonctions membres.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#154;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]  
  
##  <a name="a-namegetgmttma--ctimegetgmttm"></a><a name="getgmttm"></a>CTime::GetGmtTm  
 Obtient un **struct tm** qui contient une décomposition de l’heure contenue dans cette `CTime` objet.  
  
```  
struct tm* GetGmtTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>Paramètres  
 `ptm`  
 Pointe vers une mémoire tampon qui recevra les données de temps. Si ce pointeur est **NULL**, une exception est levée.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un renseignés **struct tm** tel que défini dans le fichier include temps. H. Consultez la page [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) pour la disposition de la structure.  
  
### <a name="remarks"></a>Remarques  
 `GetGmtTm`Retourne l’heure UTC.  
  
 `ptm` ne peut pas avoir la valeur `NULL`. Si vous souhaitez revenir à l’ancien comportement, dans lequel `ptm` peut être `NULL` pour indiquer qu’une mémoire tampon interne, alloué de manière statique doit être utilisé, puis annuler la définition de `_SECURE_ATL`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#155;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]  
  
##  <a name="a-namegethoura--ctimegethour"></a><a name="gethour"></a>CTime::GetHour  
 Retourne l’heure représentée par le `CTime` objet.  
  
```  
int GetHour() const throw(); 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Renvoie l’heure, en fonction de l’heure locale, dans la plage 0 à 23.  
  
### <a name="remarks"></a>Notes  
 Cette fonction appelle `GetLocalTm`, qui utilise de manière statique interne tampon allouée. Les données dans cette mémoire tampon sont remplacées en raison d’appels à d’autres `CTime` les fonctions membres.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#156;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]  
  
##  <a name="a-namegetlocaltma--ctimegetlocaltm"></a><a name="getlocaltm"></a>CTime::GetLocalTm  
 Obtient un **struct tm** contenant une décomposition de l’heure contenue dans cette `CTime` objet.  
  
```  
struct tm* GetLocalTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>Paramètres  
 `ptm`  
 Pointe vers une mémoire tampon qui recevra les données de temps. Si ce pointeur est **NULL**, une exception est levée.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un renseignés **struct tm** tel que défini dans le fichier include temps. H. Consultez la page [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) pour la disposition de la structure.  
  
### <a name="remarks"></a>Remarques  
 `GetLocalTm`Retourne l’heure locale.  
  
 `ptm` ne peut pas avoir la valeur `NULL`. Si vous souhaitez revenir à l’ancien comportement, dans lequel `ptm` peut être `NULL` pour indiquer qu’une mémoire tampon interne, alloué de manière statique doit être utilisé, puis annuler la définition de `_SECURE_ATL`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#157;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]  
  
##  <a name="a-namegetminutea--ctimegetminute"></a><a name="getminute"></a>CTime::GetMinute  
 Retourne la minute représentée par le `CTime` objet.  
  
```  
int GetMinute() const throw(); 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne les minutes, en fonction de l’heure locale, dans la plage 0 à 59.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction appelle `GetLocalTm`, qui utilise de manière statique interne tampon allouée. Les données dans cette mémoire tampon sont remplacées en raison d’appels à d’autres `CTime` les fonctions membres.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetHour](#gethour).  
  
##  <a name="a-namegetmontha--ctimegetmonth"></a><a name="getmonth"></a>CTime::GetMonth  
 Retourne le mois représenté par le `CTime` objet.  
  
```  
int GetMonth() const throw(); 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le mois, en fonction de l’heure locale, dans la plage 1 à 12 (1 = janvier).  
  
### <a name="remarks"></a>Remarques  
 Cette fonction appelle `GetLocalTm`, qui utilise de manière statique interne tampon allouée. Les données dans cette mémoire tampon sont remplacées en raison d’appels à d’autres `CTime` les fonctions membres.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetDay](#getday).  
  
##  <a name="a-namegetseconda--ctimegetsecond"></a><a name="getsecond"></a>CTime::GetSecond  
 Retourne le second, représenté par le `CTime` objet.  
  
```  
int GetSecond() const throw(); 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la seconde, en fonction de l’heure locale, dans la plage 0 à 59.  
  
### <a name="remarks"></a>Notes  
 Cette fonction appelle `GetLocalTm`, qui utilise de manière statique interne tampon allouée. Les données dans cette mémoire tampon sont remplacées en raison d’appels à d’autres `CTime` les fonctions membres.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetHour](#gethour).  
  
##  <a name="a-namegettimea--ctimegettime"></a><a name="gettime"></a>CTime::GetTime  
 Retourne un **__time64_t** la valeur de la donnée `CTime` objet.  
  
```  
__time64_t GetTime() const throw(); 
```  
  
### <a name="return-value"></a>Valeur de retour  
 **GetTime** renvoie le nombre de secondes entre actuel `CTime` objet et le 1er janvier 1970.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#158;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]  
  
##  <a name="a-namegetyeara--ctimegetyear"></a><a name="getyear"></a>CTime::GetYear  
 Retourne l’année représentée par le `CTime` objet.  
  
```  
int GetYear();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’année, en fonction de l’heure locale, dans la plage janvier 1,1970, à 18 janvier 2038 (inclus).  
  
### <a name="remarks"></a>Remarques  
 Cette fonction appelle `GetLocalTm`, qui utilise de manière statique interne tampon allouée. Les données dans cette mémoire tampon sont remplacées en raison d’appels à d’autres `CTime` les fonctions membres.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [GetDay](#getday).  
  
##  <a name="a-nameoperatoreqa--ctimeoperator-"></a><a name="operator_eq"></a>CTime::operator =  
 L’opérateur d’assignation.  
  
```  
CTime& operator=(__time64_t time) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `time`  
 La valeur de la nouvelle date/heure.  
  
### <a name="return-value"></a>Valeur de retour  
 Mise à jour `CTime` objet.  
  
### <a name="remarks"></a>Notes  
 Cet opérateur d’assignation surchargés copie la source dans ce `CTime` objet. Le stockage interne dans un `CTime` objet est indépendant du fuseau horaire. Conversion de fuseau horaire n’est pas nécessaire lors de l’attribution.  
  
##  <a name="a-nameoperatoradd-a--ctimeoperator---"></a><a name="operator_add_-"></a>CTime::operator +, -  
 Ces opérateurs ajouter ou soustraire `CTimeSpan` et `CTime` objets.  
  
```  
CTime operator+(CTimeSpan timeSpan) const throw(); 
CTime operator-(CTimeSpan timeSpan) const throw(); 
CTimeSpan operator-(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>Paramètres  
 *intervalle de temps*  
 Le `CTimeSpan` objet doit être ajoutée ou soustraite.  
  
 `time`  
 Le `CTime` objet à soustraire.  
  
### <a name="return-value"></a>Valeur de retour  
 A `CTime` ou `CTimeSpan` objet représentant le résultat de l’opération.  
  
### <a name="remarks"></a>Remarques  
 `CTime`les objets représentent l’heure absolue, `CTimeSpan` objets représentent l’heure relative. Les deux premiers opérateurs permettent d’ajouter et de soustraire `CTimeSpan` vers et à partir des objets `CTime` objets. Le troisième opérateur vous permet de soustraire un `CTime` objet à partir d’un autre afin de produire un `CTimeSpan` objet.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#159;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]  
  
##  <a name="a-nameoperatoraddeq-eqa--ctimeoperator---"></a><a name="operator_add_eq_-_eq"></a>CTime::operator +=, =  
 Ces opérateurs ajouter ou soustraire un `CTimeSpan` objet vers et depuis cette `CTime` objet.  
  
```  
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `span`  
 Le `CTimeSpan` objet doit être ajoutée ou soustraite.  
  
### <a name="return-value"></a>Valeur de retour  
 Mise à jour `CTime` objet.  
  
### <a name="remarks"></a>Remarques  
 Ces opérateurs permettent d’ajouter et de soustraire un `CTimeSpan` objet vers et depuis cette `CTime` objet.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities&#160;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]  
  
##  <a name="a-nameserialize64a--ctimeserialize64"></a><a name="serialize64"></a>CTime::Serialize64  
  
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
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [Classe CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [ATL et MFC des Classes partagées](../../atl-mfc-shared/atl-mfc-shared-classes.md)



