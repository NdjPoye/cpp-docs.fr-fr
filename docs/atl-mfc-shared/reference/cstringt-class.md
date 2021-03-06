---
title: Classe CStringT | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringT
- ATLSTR/ATL::CStringT
- ATLSTR/ATL::CStringT::CStringT
- ATLSTR/ATL::CStringT::AllocSysString
- ATLSTR/ATL::CStringT::AnsiToOem
- ATLSTR/ATL::CStringT::AppendFormat
- ATLSTR/ATL::CStringT::Collate
- ATLSTR/ATL::CStringT::CollateNoCase
- ATLSTR/ATL::CStringT::Compare
- ATLSTR/ATL::CStringT::CompareNoCase
- ATLSTR/ATL::CStringT::Delete
- ATLSTR/ATL::CStringT::Find
- ATLSTR/ATL::CStringT::FindOneOf
- ATLSTR/ATL::CStringT::Format
- ATLSTR/ATL::CStringT::FormatMessage
- ATLSTR/ATL::CStringT::FormatMessageV
- ATLSTR/ATL::CStringT::FormatV
- ATLSTR/ATL::CStringT::GetEnvironmentVariable
- ATLSTR/ATL::CStringT::Insert
- ATLSTR/ATL::CStringT::Left
- ATLSTR/ATL::CStringT::LoadString
- ATLSTR/ATL::CStringT::MakeLower
- ATLSTR/ATL::CStringT::MakeReverse
- ATLSTR/ATL::CStringT::MakeUpper
- ATLSTR/ATL::CStringT::Mid
- ATLSTR/ATL::CStringT::OemToAnsi
- ATLSTR/ATL::CStringT::Remove
- ATLSTR/ATL::CStringT::Replace
- ATLSTR/ATL::CStringT::ReverseFind
- ATLSTR/ATL::CStringT::Right
- ATLSTR/ATL::CStringT::SetSysString
- ATLSTR/ATL::CStringT::SpanExcluding
- ATLSTR/ATL::CStringT::SpanIncluding
- ATLSTR/ATL::CStringT::Tokenize
- ATLSTR/ATL::CStringT::Trim
- ATLSTR/ATL::CStringT::TrimLeft
- ATLSTR/ATL::CStringT::TrimRight
- CSTRINGT/CStringT
- CSTRINGT/CStringT::CStringT
- CSTRINGT/CStringT::AllocSysString
- CSTRINGT/CStringT::AnsiToOem
- CSTRINGT/CStringT::AppendFormat
- CSTRINGT/CStringT::Collate
- CSTRINGT/CStringT::CollateNoCase
- CSTRINGT/CStringT::Compare
- CSTRINGT/CStringT::CompareNoCase
- CSTRINGT/CStringT::Delete
- CSTRINGT/CStringT::Find
- CSTRINGT/CStringT::FindOneOf
- CSTRINGT/CStringT::Format
- CSTRINGT/CStringT::FormatMessage
- CSTRINGT/CStringT::FormatMessageV
- CSTRINGT/CStringT::FormatV
- CSTRINGT/CStringT::GetEnvironmentVariable
- CSTRINGT/CStringT::Insert
- CSTRINGT/CStringT::Left
- CSTRINGT/CStringT::LoadString
- CSTRINGT/CStringT::MakeLower
- CSTRINGT/CStringT::MakeReverse
- CSTRINGT/CStringT::MakeUpper
- CSTRINGT/CStringT::Mid
- CSTRINGT/CStringT::OemToAnsi
- CSTRINGT/CStringT::Remove
- CSTRINGT/CStringT::Replace
- CSTRINGT/CStringT::ReverseFind
- CSTRINGT/CStringT::Right
- CSTRINGT/CStringT::SetSysString
- CSTRINGT/CStringT::SpanExcluding
- CSTRINGT/CStringT::SpanIncluding
- CSTRINGT/CStringT::Tokenize
- CSTRINGT/CStringT::Trim
- CSTRINGT/CStringT::TrimLeft
- CSTRINGT/CStringT::TrimRight
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f8a66f87b3c4a2c6712a1db93f97361a25b6955
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="cstringt-class"></a>CStringT (classe)
Cette classe représente un `CStringT` objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
 
template<typename BaseType, class StringTraits>  
class CStringT :   
public CSimpleStringT<BaseType,
                      _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                      ::c_bIsMFCDLLTraits>  
 
```  
  
#### <a name="parameters"></a>Paramètres  
 `BaseType`  
 Le type de caractère de la classe string. Il peut s'agir d'une des valeurs suivantes :  
  
- `char` (pour les chaînes de caractères ANSI).  
  
- `wchar_t` (pour les chaînes de caractères Unicode).  
  
- **TCHAR** (pour les chaînes de caractères ANSI et Unicode).  
  
 `StringTraits`  
 Détermine si la classe string a besoin de prise en charge de la bibliothèque Runtime C (CRT) et où se trouvent les ressources de type chaîne. Il peut s'agir d'une des valeurs suivantes :  
  
- **StrTraitATL < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     La classe nécessite la prise en charge CRT et recherche les chaînes de ressources dans le module spécifié par `m_hInstResource` (il s’agit d’un membre de classe de module de l’application).  
  
- **StrTraitATL < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsOS < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     La classe ne nécessite pas de prise en charge CRT et recherche les chaînes de ressources dans le module spécifié par `m_hInstResource` (il s’agit d’un membre de classe de module de l’application).  
  
- **StrTraitMFC < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsCRT < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     La classe nécessite la prise en charge CRT et recherche les chaînes de ressources à l’aide de l’algorithme de recherche MFC standard.  
  
- **StrTraitMFC < wchar_t** &#124; `char` &#124; **TCHAR, ChTraitsOS < wchar_t** &#124; `char` &#124; **TCHAR >>**  
  
     Prise en charge CRT et recherche les chaînes de ressources à l’aide de l’algorithme de recherche standard MFC, la classe n’est pas nécessaire.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CStringT::CStringT](#cstringt)|Construit un `CStringT` objet de différentes manières.|  
|[CStringT :: ~ CStringT](#_dtorcstringt)|Détruit un objet `CStringT`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CStringT::AllocSysString](#allocsysstring)|Alloue un `BSTR` de `CStringT` données.|  
|[CStringT::AnsiToOem](#ansitooem)|Effectue une conversion de place dans le jeu de caractères ANSI pour le jeu de caractères OEM.|  
|[CStringT::AppendFormat](#appendformat)|Ajoute des données mises en forme à un `CStringT` objet.|  
|[CStringT::Collate](#collate)|Compare deux chaînes (la casse, utilise les informations spécifiques aux paramètres régionaux).|  
|[CStringT::CollateNoCase](#collatenocase)|Compare deux chaînes (non-respect de la casse, utilise les informations spécifiques aux paramètres régionaux).|  
|[CStringT::Compare](#compare)|Compare deux chaînes (sensible à la casse).|  
|[CStringT::CompareNoCase](#comparenocase)|Compare deux chaînes (sensible à la casse).|  
|[CStringT::Delete](#delete)|Supprime un ou plusieurs caractères à partir d’une chaîne.|  
|[CStringT::Find](#find)|Recherche un caractère ou une sous-chaîne à l’intérieur d’une chaîne plus grande.|  
|[CStringT::FindOneOf](#findoneof)|Recherche le premier caractère correspondant à partir d’un jeu.|  
|[CStringT::Format](#format)|Met en forme la chaîne en tant que `sprintf` est.|  
|[CStringT::FormatMessage](#formatmessage)|Met en forme une chaîne de message.|  
|[CStringT::FormatMessageV](#formatmessagev)|Met en forme une chaîne de message à l’aide d’une liste d’arguments variable.|  
|[CStringT::FormatV](#formatv)|Met en forme la chaîne à l’aide d’une liste d’arguments de variables.|  
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|Définit la chaîne à la valeur de la variable d’environnement spécifié.|  
|[CStringT::Insert](#insert)|Insère un caractère unique ou une sous-chaîne à l’index donné dans la chaîne.|  
|[CStringT::Left](#left)|Extrait la partie gauche d’une chaîne.|  
|[CStringT::LoadString](#loadstring)|Charge un existant `CStringT` objet à partir d’une ressource Windows.|  
|[CStringT::MakeLower](#makelower)|Convertit tous les caractères de cette chaîne en caractères minuscules.|  
|[CStringT::MakeReverse](#makereverse)|Inverse la chaîne.|  
|[CStringT::MakeUpper](#makeupper)|Convertit tous les caractères de cette chaîne en caractères majuscules.|  
|[CStringT::Mid](#mid)|Extrait la partie centrale d’une chaîne.|  
|[CStringT::OemToAnsi](#oemtoansi)|Effectue une conversion de place dans le jeu de caractères OEM pour le jeu de caractères ANSI.|  
|[CStringT::Remove](#remove)|Supprime indiqué de caractères d’une chaîne.|  
|[CStringT::Replace](#replace)|Remplace indiqué caractères avec d’autres caractères.|  
|[CStringT::ReverseFind](#reversefind)|Recherche un caractère à l’intérieur d’une chaîne plus grande ; démarre à partir de la fin.|  
|[CStringT::Right](#right)|Extrait la partie droite d’une chaîne.|  
|[CStringT::SetSysString](#setsysstring)|Définit un existant `BSTR` objet avec les données d’une `CStringT` objet.|  
|[CStringT::SpanExcluding](#spanexcluding)|Extrait les caractères de la chaîne, en commençant par le premier caractère qui ne sont pas dans le jeu de caractères identifié par `pszCharSet`.|  
|[CStringT::SpanIncluding](#spanincluding)|Extrait une sous-chaîne qui contient uniquement les caractères dans un jeu.|  
|[CStringT::Tokenize](#tokenize)|Extraits spécifié des jetons dans une chaîne cible.|  
|[CStringT::Trim](#trim)|Supprime tous les caractères d’espace de début et de fin de la chaîne.|  
|[CStringT::TrimLeft](#trimleft)|Supprime les espaces blancs de début de la chaîne.|  
|[CStringT::TrimRight](#trimright)|Supprime de la chaîne de caractères d’espace blanc de fin.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[opérateur =](#operator_eq)|Affecte une nouvelle valeur à un `CStringT` objet.|  
|[CStringT::operator +](#operator_add)|Concatène deux chaînes ou un caractère et une chaîne.|  
|[CStringT::operator +=](#operator_add_eq)|Concatène une nouvelle chaîne à la fin d’une chaîne existante.|  
|[CStringT::operator ==](#operator_eq_eq)|Détermine si deux chaînes sont logiquement égales.|  
|[CStringT::operator ! =](#operator_neq)|Détermine si deux chaînes sont logiquement pas égaux.|  
|[CStringT::operator &lt;](#operator_lt)|Détermine si la chaîne sur le côté gauche de l’opérateur est inférieur à la chaîne située à droite.|  
|[CStringT::operator &gt;](#operator_gt)|Détermine si la chaîne sur le côté gauche de l’opérateur est supérieure à la chaîne située à droite.|  
|[CStringT::operator &lt;=](#operator_lt_eq)|Détermine si la chaîne sur le côté gauche de l’opérateur est inférieur ou égal à la chaîne située à droite.|  
|[CStringT::operator &gt;=](#operator_gt_eq)|Détermine si la chaîne sur le côté gauche de l’opérateur est supérieur ou égal à la chaîne située à droite.|  
  
## <a name="remarks"></a>Notes  
 `CStringT` hérite de [CSimpleStringT classe](../../atl-mfc-shared/reference/csimplestringt-class.md). Les fonctionnalités avancées, telles que de la manipulation de caractères, de classement et de recherche, sont implémentées par `CStringT`.  
  
> [!NOTE]
> `CStringT` les objets sont capables de lever des exceptions. Cela se produit lorsqu’un `CStringT` objet s’exécute en dehors de la mémoire pour une raison quelconque.  
  
 A `CStringT` objet se compose d’une séquence de longueur variable de caractères. `CStringT` Fournit des fonctions et opérateurs à l’aide d’une syntaxe semblable à celle de base. Concaténation et les opérateurs de comparaison, ainsi que de la gestion simplifiée de la mémoire, rendent `CStringT` objets plus faciles à utiliser que les tableaux de caractères ordinaires.  
  
> [!NOTE]
>  Bien qu’il soit possible de créer `CStringT` instances qui contiennent des caractères null incorporés, nous vous recommandons par rapport à elle. Appel de méthodes et opérateurs sur `CStringT` objets qui contiennent des caractères null incorporés peuvent produire des résultats inattendus.  
  
 À l’aide de différentes combinaisons de le `BaseType` et `StringTraits` paramètres, `CStringT` objets peut sont fournis dans les types suivants, qui ont été prédéfinis par les bibliothèques ATL.  
  
 Si vous utilisez dans une application ATL :  
  
 `CString`, `CStringA`, et `CStringW` sont exportés à partir de la DLL MFC (MFC90. (DLL), jamais à partir de la DLL d’utilisateur. Cela permet d’éviter `CStringT` d’être défini plusieurs fois.  
  
> [!NOTE]
>  Si votre code contient des erreurs de l’éditeur de liens qui est décrit dans la solution de contournement [Linking Errors When You Import CString-Derived Classes » (Q309801)](https://support.microsoft.com/help/309801/you-may-receive-an-lnk2019-error-message-when-you-build-a-visual-c-200), vous devez supprimer ce code. Il n’est plus nécessaire.  
  
 Les types de chaîne suivants sont disponibles dans des applications MFC :  
  
|Type de CStringT|Déclaration|  
|-------------------|-----------------|  
|`CStringA`|Un caractère ANSI de type chaîne avec la prise en charge CRT.|  
|`CStringW`|Un caractère Unicode de type chaîne avec la prise en charge CRT.|  
|`CString`|Types de caractères ANSI et Unicode avec prise en charge de CRT.|  
  
 La chaîne suivante types sont disponibles dans les projets où **ATL_CSTRING_NO_CRT** est défini :  
  
|Type de CStringT|Déclaration|  
|-------------------|-----------------|  
|**CAtlStringA**|Un caractère ANSI de type chaîne sans prise en charge de CRT.|  
|**CAtlStringW**|Un caractère Unicode de type chaîne sans prise en charge de CRT.|  
|**CAtlString**|Types de caractères ANSI et Unicode sans prise en charge de CRT.|  
  
 La chaîne suivante types sont disponibles dans les projets où **ATL_CSTRING_NO_CRT** n’est pas défini :  
  
|Type de CStringT|Déclaration|  
|-------------------|-----------------|  
|**CAtlStringA**|Un caractère ANSI de type chaîne avec la prise en charge CRT.|  
|**CAtlStringW**|Un caractère Unicode de type chaîne avec la prise en charge CRT.|  
|**CAtlString**|Types de caractères ANSI et Unicode avec prise en charge de CRT.|  
  
 `CString` objets présentent également les caractéristiques suivantes :  
  
- `CStringT` objets peuvent augmenter en conséquence des opérations de concaténation.  
  
- `CStringT` les objets suivent la « sémantique des valeurs ». Imaginez un `CStringT` objet sous forme de chaîne réelle, et non comme un pointeur vers une chaîne.  
  
-   Vous pouvez utiliser librement `CStringT` objets `PCXSTR` les arguments de fonction.  
  
-   Gestion de mémoire personnalisée pour les mémoires tampons de chaîne. Pour plus d’informations, consultez [gestion de la mémoire et CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="cstringt-predefined-types"></a>CStringT des Types prédéfinis.  
 Étant donné que `CStringT` utilise un argument de modèle pour définir le type de caractère (soit [wchar_t](../../c-runtime-library/standard-types.md) ou [char](../../c-runtime-library/standard-types.md)) pris en charge, les types de paramètres de méthode peuvent être complexes à des moments. Pour simplifier ce problème, un ensemble de types prédéfinis est défini et utilisé sur le `CStringT` classe. Le tableau suivant répertorie les différents types :  
  
|Name|Description|  
|----------|-----------------|  
|`XCHAR`|Un caractère unique (soit `wchar_t` ou `char`) avec le même type de caractère que le `CStringT` objet.|  
|**YCHAR**|Un caractère unique (soit `wchar_t` ou `char`) avec le type de caractère autre que le `CStringT` objet.|  
|`PXSTR`|Un pointeur vers une chaîne de caractères (soit `wchar_t` ou `char`) avec le même type de caractère que le `CStringT` objet.|  
|**PYSTR**|Un pointeur vers une chaîne de caractères (soit `wchar_t` ou `char`) avec le type de caractère autre que le `CStringT` objet.|  
|`PCXSTR`|Un pointeur vers un **const** chaîne de caractères (soit `wchar_t` ou `char`) avec le même type de caractère que le `CStringT` objet.|  
|**PCYSTR**|Un pointeur vers un **const** chaîne de caractères (soit `wchar_t` ou `char`) avec le type de caractère autre que le `CStringT` objet.|  
  
> [!NOTE]
>  Code qui utilisait précédemment des méthodes non documentées de `CString` (tel que **AssignCopy**) doit être remplacé par le code qui utilise les méthodes suivantes documentées de `CStringT` (tel que `GetBuffer` ou `ReleaseBuffer`). Ces méthodes sont héritées de `CSimpleStringT`.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)  
  
 `CStringT`  
  
## <a name="requirements"></a>Spécifications  
  
|Header|Utilisation pour|  
|------------|-------------|  
|CStringT.h|Objets de chaîne MFC uniquement|  
|atlstr.h|Objets de chaîne non-MFC|  
  
##  <a name="allocsysstring"></a>  CStringT::AllocSysString  
 Alloue une chaîne compatibles Automation du type `BSTR` et copie le contenu de la `CStringT` objet, y compris le caractère null de fin.  
  
```  
BSTR AllocSysString() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La chaîne nouvellement allouée.  
  
### <a name="remarks"></a>Notes  
 Dans les programmes MFC, un [CMemoryException classe](../../mfc/reference/cmemoryexception-class.md) est levée en cas de mémoire insuffisante. Dans les programmes ATL, un [CAtlException](../../atl/reference/catlexception-class.md) est levée. Cette fonction est normalement utilisée pour retourner des chaînes pour l’automatisation.  
  

 En règle générale, si cette chaîne est passée à une fonction COM comme un [in] paramètre, puis il requiert que l’appelant de libérer la chaîne. Cela est possible à l’aide de [SysFreeString](https://msdn.microsoft.com/library/windows/desktop/ms221481.aspx), comme décrit dans le Kit de développement logiciel Windows. Pour plus d’informations, consultez [affectation et libération de la mémoire pour un BSTR](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md).  
  
 Pour plus d’informations sur les fonctions d’allocation OLE dans Windows, consultez [SysAllocString](https://msdn.microsoft.com/library/windows/desktop/ms221458.aspx) dans le Kit de développement logiciel Windows.  

  
### <a name="example"></a>Exemple  
 L'exemple suivant montre l'utilisation de `CStringT::AllocSysString`.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]  
  
##  <a name="ansitooem"></a>  CStringT::AnsiToOem  
 Convertit tous les caractères de cette `CStringT` objet dans le jeu de caractères ANSI pour le jeu de caractères OEM.  
  
```  
void AnsiToOem();
```  
  
### <a name="remarks"></a>Notes  
 La fonction n’est pas disponible si `_UNICODE` est défini.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]  
  
##  <a name="appendformat"></a>  CStringT::AppendFormat  
 Ajoute des données mises en forme à un `CStringT` objet.  
  
```  
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pszFormat`  
 Une chaîne de format de contrôle.  
  
 `nFormatID`  
 L’identificateur de ressource de chaîne qui contient la chaîne de format de contrôle.  
  
 `argument`  
 Arguments facultatifs.  
  
### <a name="remarks"></a>Notes  
 Cette fonction met en forme et ajoute une série de caractères et de valeurs dans le `CStringT`. Chaque argument facultatif (le cas échéant) est converti et ajouté en fonction de la spécification de format correspondante dans `pszFormat` ou à partir de la ressource de chaîne identifié par `nFormatID`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]  
  
##  <a name="collate"></a>  CStringT::Collate  
 Compare deux chaînes à l’aide de la fonction de texte générique `_tcscoll`.  
  
```  
int Collate(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `psz`  
 La chaîne utilisée pour la comparaison.  
  
### <a name="return-value"></a>Valeur de retour  
 Zéro si les chaînes sont identiques, < 0 si ce `CStringT` objet est inférieur à `psz`, ou > 0 si ce `CStringT` objet est supérieur à `psz`.  
  
### <a name="remarks"></a>Notes  
 La fonction de texte générique `_tcscoll`, qui est défini dans TCHAR. H, correspond à une `strcoll`, `wcscoll`, ou `_mbscoll`, selon le jeu de caractères qui est défini au moment de la compilation. Chaque fonction effectue une comparaison respectant la casse des chaînes en fonction de la page de codes actuellement en cours d’utilisation. Pour plus d’informations, consultez [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).  
  
##  <a name="collatenocase"></a>  CStringT::CollateNoCase  
 Compare deux chaînes à l’aide de la fonction de texte générique `_tcscoll`.  
  
```  
int CollateNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `psz`  
 La chaîne utilisée pour la comparaison.  
  
### <a name="return-value"></a>Valeur de retour  
 Zéro si les chaînes sont identiques (ignorer la casse), < 0 si ce `CStringT` objet est inférieur à `psz` (ignorer la casse), ou > 0 si ce `CStringT` objet est supérieur à `psz` (ignorer la casse).  
  
### <a name="remarks"></a>Notes  
 La fonction de texte générique `_tcscoll`, qui est défini dans TCHAR. H, correspond à une `stricoll`, `wcsicoll`, ou `_mbsicoll`, selon le jeu de caractères qui est défini au moment de la compilation. Chaque fonction effectue une comparaison respectant la casse des chaînes, en fonction de la page de codes en cours d’utilisation. Pour plus d’informations, consultez [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]  
  
##  <a name="compare"></a>  CStringT::Compare  
 Compare deux chaînes (sensible à la casse).  
  
```  
int Compare(PCXSTR psz) const; 
```  
  
### <a name="parameters"></a>Paramètres  
 `psz`  
 La chaîne utilisée pour la comparaison.  
  
### <a name="return-value"></a>Valeur de retour  
 Zéro si les chaînes sont identiques, < 0 si ce `CStringT` objet est inférieur à `psz`, ou > 0 si ce `CStringT` objet est supérieur à `psz`.  
  
### <a name="remarks"></a>Notes  
 La fonction de texte générique `_tcscmp`, qui est défini dans TCHAR. H, correspond à une `strcmp`, `wcscmp`, ou `_mbscmp`, selon le jeu de caractères qui est défini au moment de la compilation. Chaque fonction effectue une comparaison respectant la casse des chaînes et n’est pas affectée par les paramètres régionaux. Pour plus d’informations, consultez [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md).  
  
 Si la chaîne contient des valeurs null incorporées, à des fins de comparaison, la chaîne est considérée être tronquées au premier caractère null incorporé.  
  
### <a name="example"></a>Exemple  
 L'exemple suivant montre l'utilisation de `CStringT::Compare`.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]  
  
##  <a name="comparenocase"></a>  CStringT::CompareNoCase  
 Compare deux chaînes (sensible à la casse).  
  
```  
int CompareNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `psz`  
 La chaîne utilisée pour la comparaison.  
  
### <a name="return-value"></a>Valeur de retour  
 Zéro si les chaînes sont identiques (ignorer la casse), < 0 si ce `CStringT` objet est inférieur à `psz` (ignorer la casse), ou > 0 si ce `CStringT` objet est supérieur à `psz` (ignorer la casse).  
  
### <a name="remarks"></a>Notes  
 La fonction de texte générique `_tcsicmp`, qui est défini dans TCHAR. H, correspond à une `_stricmp`, `_wcsicmp` ou `_mbsicmp`, selon le jeu de caractères qui est défini au moment de la compilation. Chaque fonction effectue une comparaison respectant la casse des chaînes. La comparaison dépend de la `LC_CTYPE` aspect des paramètres régionaux, mais pas `LC_COLLATE`. Pour plus d’informations, consultez [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]  
  
##  <a name="cstringt"></a>  CStringT::CStringT  
 Construit un objet `CStringT`.  
  
```  
CStringT() throw() :   
    CThisSimpleString(StringTraits::GetDefaultManager());
 
explicit CStringT(IAtlStringMgr* pStringMgr) throw() :   
    CThisSimpleString( pStringMgr); 

CStringT(const VARIANT& varSrc);
 
CStringT(const VARIANT& varSrc, IAtlStringMgr* pStringMgr);
 
CStringT(const CStringT& strSrc) :   
    CThisSimpleString( strSrc);

 operator CSimpleStringT<
                    BaseType, 
                    !_CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                    :: c_bIsMFCDLLTraits> &()  
 
template <bool bMFCDLL>  
CStringT(const CSimpleStringT<BaseType, bMFCDLL>& strSrc) :   
    CThisSimpleString( strSrc);
 
template <class SystemString>  
CStringT(SystemString^ pString) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(const YCHAR* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(LPCSTR pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CStringT(LPCWSTR pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CSTRING_EXPLICIT CStringT(const unsigned char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
/*CSTRING_EXPLICIT*/ CStringT(char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(unsigned char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(wchar_t* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const unsigned char* pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CSTRING_EXPLICIT CStringT(char ch, int nLength = 1) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(wchar_t ch, int nLength = 1) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pch, int nLength) :   
    CThisSimpleString( pch, nLength, StringTraits::GetDefaultManager());
 
CStringT(const YCHAR* pch, int nLength) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pch, int nLength, AtlStringMgr* pStringMgr) :   
    CThisSimpleString( pch, nLength, pStringMgr);
 
CStringT(const YCHAR* pch, int nLength, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
```  
  
### <a name="parameters"></a>Paramètres  
 `pch`  
 Un pointeur vers un tableau de caractères de longueur `nLength`pas se terminant par null.  
  
 `nLength`  
 Le nombre de caractères dans `pch`.  
  
 `ch`  
 Un caractère unique.  
  
 `pszSrc`  
 Une chaîne se terminant par null à copier dans cette `CStringT` objet.  
  
 `pStringMgr`  
 Un pointeur vers le Gestionnaire de mémoire pour le `CStringT` objet. Pour plus d’informations sur `IAtlStringMgr` et gestion de la mémoire pour `CStringT`, consultez [gestion de la mémoire avec CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 `strSrc`  
 Existant `CStringT` objet doit être copié dans ce `CStringT` objet. Pour plus d’informations sur `CThisString` et `CThisSimpleString`, consultez la section Notes.  
  
 `varSrc`  
 Un objet de type variant à copier dans cette `CStringT` objet.  
  
 `BaseType`  
 Le type de caractère de la classe string. Il peut s'agir d'une des valeurs suivantes :  
  
 `char` (pour les chaînes de caractères ANSI).  
  
 `wchar_t` (pour les chaînes de caractères Unicode).  
  
 `TCHAR` (pour les chaînes ANSI et Unicode caractère).  
  
 `bMFCDLL`  
 Valeur booléenne qui spécifie si le projet est une DLL MFC (TRUE) ou non (FALSE).  
  
 `SystemString`  
 Doit être `System::String`, et le projet doit être compilé avec/CLR.  
  
 `pString`  
 Un handle pour un `CStringT` objet.  
  
### <a name="remarks"></a>Notes  
 Étant donné que les constructeurs copient les données d’entrée dans le nouveau stockage alloué, vous devez être conscient que la mémoire peuvent entraîner des exceptions. Notez que certaines de ces constructeurs agissent comme des fonctions de conversion. Cela vous permet de remplacer, par exemple, un `LPTSTR` où un `CStringT` objet est attendu.  
  
- `CStringT`( `LPCSTR` `lpsz` ) : Construit Unicode `CStringT` à partir d’une chaîne ANSI. Vous pouvez également utiliser ce constructeur pour charger une ressource de chaîne, comme indiqué dans l’exemple ci-dessous.  
  
- `CStringT(` `LPCWSTR` `lpsz` ) : Construit un `CStringT` à partir d’une chaîne Unicode.  
  
- `CStringT`( `const unsigned char*` `psz` ) : Vous permet de construire un `CStringT` d’un pointeur vers `unsigned char`.  
  
> [!NOTE]
>  Définir le **_CSTRING_DISABLE_NARROW_WIDE_CONVERSION** macro pour désactiver la conversion de chaînes implicite entre [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] et [!INCLUDE[TLA#tla_unicode](../../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] chaînes. La macro exclut à partir des constructeurs de compilation qui prennent en charge la conversion.  
  
 Notez que la `strSrc` paramètre peut être soit un `CStringT` ou `CThisSimpleString` objet. Pour `CStringT`, utilisez une de ses instanciations par défaut ( `CString`, `CStringA`, ou `CStringW`) ; pour `CThisSimpleString`, utilisez un `this` pointeur. `CThisSimpleString` déclare une instance de la [CSimpleStringT classe](../../atl-mfc-shared/reference/csimplestringt-class.md), qui est une classe de chaîne plus petite avec des fonctionnalités intégrées de moins que la `CStringT` classe.  
  
 L’opérateur de surcharge `CSimpleStringT<>&()` construit un `CStringT` de l’objet d’un `CSimpleStringT` déclaration.  
  
> [!NOTE]
>  Bien qu’il soit possible de créer `CStringT` instances qui contiennent des caractères null incorporés, nous vous recommandons par rapport à elle. Appel de méthodes et opérateurs sur `CStringT` objets qui contiennent des caractères null incorporés peuvent produire des résultats inattendus.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]  
  
##  <a name="_dtorcstringt"></a>  CStringT :: ~ CStringT  
 Détruit le `CStringT` objet.  
  
```  
~CStringT() throw();
```  
  
### <a name="remarks"></a>Notes  
 Détruit le `CStringT` objet.  
  
##  <a name="delete"></a>  CStringT::Delete  
 Supprime un ou plusieurs caractères à partir d’une chaîne commençant par le caractère situé à l’index donné.  
  
```  
int Delete(int iIndex, int nCount = 1);
```  
  
### <a name="parameters"></a>Paramètres  
 `iIndex`  
 Index de base zéro du premier caractère dans le `CStringT` objet à supprimer.  
  
 `nCount`  
 Le nombre de caractères à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur de la chaîne modifiée.  
  
### <a name="remarks"></a>Notes  
 Si `nCount` est plus long que la chaîne, le reste de la chaîne sera supprimée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]  
  
```Output  
Before: Soccer is best,
    but hockey is quicker!  
After: Soccer best,
    but hockey is quicker!  
```  
  
##  <a name="find"></a>  CStringT::Find  
 Cette chaîne de recherche la première correspondance d’un caractère ou d’une sous-chaîne.  
  
```  
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pszSub`  
 Sous-chaîne à rechercher.  
  
 `iStart`  
 L’index du caractère dans la chaîne pour commencer la recherche, ou 0 pour démarrer à partir du début.  
  
 `ch`  
 Un caractère unique à rechercher.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro du premier caractère dans ce `CStringT` objet qui correspond à la sous-chaîne demandée ou les caractères ; -1 si la sous-chaîne ou un caractère est introuvable.  
  
### <a name="remarks"></a>Notes  
 La fonction est surchargée pour accepter les caractères uniques (similaire à la fonction runtime `strchr`) et les chaînes (semblable à `strstr`).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]  
  
##  <a name="findoneof"></a>  CStringT::FindOneOf  
 Recherche de cette chaîne pour le premier caractère qui correspond à n’importe quel caractère contenue dans `pszCharSet`.  
  
```  
int FindOneOf(PCXSTR pszCharSet) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pszCharSet`  
 Chaîne contenant des caractères pour la correspondance.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro du premier caractère dans cette chaîne se trouve également dans `pszCharSet`; -1 si aucune correspondance.  
  
### <a name="remarks"></a>Notes  
 Recherche la première occurrence d’un des caractères de `pszCharSet`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]  
  
##  <a name="format"></a>  CStringT::Format  
 Écrit mises en forme des données à un `CStringT` de la même façon que [sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) des formats de données dans un tableau de caractères de style C.  
  
```  
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```  
  
### <a name="parameters"></a>Paramètres  
 `nFormatID`  
 L’identificateur de ressource de chaîne qui contient la chaîne de format de contrôle.  
  
 `pszFormat`  
 Une chaîne de format de contrôle.  
  
 `argument`  
 Arguments facultatifs.  
  
### <a name="remarks"></a>Notes  
 Cette fonction met en forme et stocke une série de caractères et de valeurs dans le `CStringT`. Chaque argument facultatif (le cas échéant) est converti et sorti selon la spécification de format correspondante dans `pszFormat` ou à partir de la ressource de chaîne identifié par `nFormatID`.  
  
 L’appel échoue si l’objet de la chaîne est proposé en tant que paramètre à `Format`. Par exemple, le code suivant entraîne des résultats imprévisibles :  
  
 [!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]  
  
 Pour plus d’informations, consultez [Syntaxe de spécification de format : fonctions printf et wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]  
  
##  <a name="formatmessage"></a>  CStringT::FormatMessage  
 Met en forme une chaîne de message.  
  
```  
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```  
  
### <a name="parameters"></a>Paramètres  
 `nFormatID`  
 L’identificateur de ressource de chaîne qui contient le texte du message non mis en forme.  
  
 `pszFormat`  
 Pointe vers la chaîne de format de contrôle. Il sera analysé pour les insertions et mises en forme en conséquence. La chaîne de format est semblable à la fonction runtime `printf`-style de chaînes de format, à ceci près qu’il autorise pour les paramètres à insérer dans un ordre arbitraire.  
  
 `argument`  
 Arguments facultatifs.  
  
### <a name="remarks"></a>Notes  
 La fonction requiert une définition de message en tant qu’entrée. La définition de message est déterminée par `pszFormat` ou à partir de la ressource de chaîne identifié par `nFormatID`. La fonction copie le texte du message mis en forme à le `CStringT` objet, traitement incorporé Insérer séquences si nécessaire.  
  
> [!NOTE]
> `FormatMessage` tente d’allouer la mémoire système pour la chaîne qui vient d’être mis en forme. Si cette tentative échoue, une exception de mémoire est automatiquement levée.  
  
 Chaque insertion doit avoir une paramètre correspondant suivant le `pszFormat` ou `nFormatID` paramètre. Dans le texte du message, plusieurs séquences d’échappement sont pris en charge pour la mise en forme dynamique le message. Pour plus d’informations, consultez les fenêtres [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) fonction dans le SDK Windows.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]  
  
##  <a name="formatmessagev"></a>  CStringT::FormatMessageV  
 Met en forme une chaîne de message à l’aide d’une liste d’arguments variable.  
  
```  
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```  
  
### <a name="parameters"></a>Paramètres  
 `pszFormat`  
 Pointe vers la chaîne de format de contrôle. Il sera analysé pour les insertions et mises en forme en conséquence. La chaîne de format est semblable à la fonction runtime `printf`-style de chaînes de format, à ceci près qu’il autorise pour les paramètres à insérer dans un ordre arbitraire.  
  
 `pArgList`  
 Pointeur vers une liste d’arguments.  
  
### <a name="remarks"></a>Notes  
 La fonction requiert une définition de message en tant qu’entrée, déterminé par `pszFormat`. La fonction copie le texte du message mis en forme et une liste variable d’arguments pour le `CStringT` objet, traitement incorporé Insérer séquences si nécessaire.  
  
> [!NOTE]
> `FormatMessageV` appels [CStringT::FormatMessage](#formatmessage), qui tente d’allouer la mémoire système pour la chaîne qui vient d’être mis en forme. Si cette tentative échoue, une exception de mémoire est automatiquement levée.  
  
 Pour plus d’informations, consultez les fenêtres [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) fonction dans le SDK Windows.  
  
##  <a name="formatv"></a>  CStringT::FormatV  
 Met en forme une chaîne de message à l’aide d’une liste d’arguments variable.  
  
```  
void FormatV(PCXSTR pszFormat, va_list args);
```  
  
### <a name="parameters"></a>Paramètres  
 `pszFormat`  
 Pointe vers la chaîne de format de contrôle. Il sera analysé pour les insertions et mises en forme en conséquence. La chaîne de format est semblable à la fonction runtime `printf`-style de chaînes de format, à ceci près qu’il autorise pour les paramètres à insérer dans un ordre arbitraire.  
  
 `args`  
 Pointeur vers une liste d’arguments.  
  
### <a name="remarks"></a>Notes  
 Écrit une chaîne mise en forme et une liste variable d’arguments à une `CStringT` chaîne de la même façon que `vsprintf_s` des formats de données dans un tableau de caractères de style C.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]  
  
##  <a name="getenvironmentvariable"></a>  CStringT::GetEnvironmentVariable  
 Définit la chaîne à la valeur de la variable d’environnement spécifié.  
  
```  
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```  
  
### <a name="parameters"></a>Paramètres  
 `pszVar`  
 Pointeur vers une chaîne se terminant par null qui spécifie la variable d’environnement.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Récupère la valeur de la variable spécifiée à partir du bloc d’environnement du processus appelant. La valeur est sous la forme de chaîne de caractères se terminant par null.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]  
  
##  <a name="insert"></a>  CStringT::Insert  
 Insère un caractère unique ou une sous-chaîne à l’index donné dans la chaîne.  
  
```  
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```  
  
### <a name="parameters"></a>Paramètres  
 `iIndex`  
 L’index du caractère avant laquelle l’insertion a lieu.  
  
 `psz`  
 Pointeur vers la sous-chaîne à insérer.  
  
 `ch`  
 Le caractère à insérer.  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur de la chaîne modifiée.  
  
### <a name="remarks"></a>Notes  
 Le `iIndex` paramètre identifie le premier caractère qui sera déplacé pour libérer de l’espace pour le caractère ou la sous-chaîne. Si `nIndex` est égal à zéro, l’insertion se produiront avant de la chaîne entière. Si `nIndex` est supérieur à la longueur de la chaîne, la fonction concatène la chaîne actuelle et le nouveau matériel fourni par le `ch` ou `psz`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]  
  
##  <a name="left"></a>  CStringT::Left  
 Extrait les caractères `nCount` les plus à gauche de cet objet `CStringT` et retourne une copie de la sous-chaîne extraite.  
  
```  
CStringT Left(int nCount) const; 
```  
  
### <a name="parameters"></a>Paramètres  
 `nCount`  
 Nombre de caractères à extraire de cet objet `CStringT`.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `CStringT` qui contient une copie de la plage spécifiée des caractères. L'objet retourné par `CStringT` peut être vide.  
  
### <a name="remarks"></a>Notes  
 Si `nCount` dépasse la longueur de la chaîne, la chaîne entière est extraite. `Left` est similaire à la fonction de base `Left`.  
  
 Pour les jeux de caractères multioctets (MBCS), `nCount` traite chaque séquence de 8 bits en tant que caractère, afin que `nCount` retourne le nombre de caractères multioctets multiplié par deux.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]  
  
##  <a name="loadstring"></a>  CStringT::LoadString  
 Lit une chaîne de ressource Windows, identifiée par `nID`, dans une `CStringT` objet.  
  
```  
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `hInstance`  
 Handle vers l’instance du module.  
  
 `nID`  
 Un ID de ressource de chaîne Windows.  
  
 `wLanguageID`  
 La langue de la ressource de chaîne.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la charge de ressources a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Charge la ressource de chaîne ( `nID`) à partir du module spécifié ( `hInstance`) à l’aide de la langue spécifiée ( `wLanguage`).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]  
  
##  <a name="makelower"></a>  CStringT::MakeLower  
 Convertit le `CStringT` objet à une chaîne en minuscules.  
  
```  
CStringT& MakeLower();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La chaîne obtenue en minuscules.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]  
  
##  <a name="makereverse"></a>  CStringT::MakeReverse  
 Inverse l’ordre des caractères dans le `CStringT` objet.  
  
```  
CStringT& MakeReverse();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Résultant inversé la chaîne.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]  
  
##  <a name="makeupper"></a>  CStringT::MakeUpper  
 Convertit le `CStringT` objet à une chaîne en majuscules.  
  
```  
CStringT& MakeUpper();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La chaîne obtenue en majuscules.  
  
### <a name="remarks"></a>Notes  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]  
  
##  <a name="mid"></a>  CStringT::Mid  
 Extrait une sous-chaîne de longueur `nCount` caractères à partir de ce `CStringT` objet, en commençant à la position `iFirst` (base zéro).  
  
```  
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const; 
```  
  
### <a name="parameters"></a>Paramètres  
 `iFirst`  
 Index de base zéro du premier caractère dans ce `CStringT` objet doit être inclus dans la sous-chaîne extraite.  
  
 `nCount`  
 Nombre de caractères à extraire de cet objet `CStringT`. Si ce paramètre n’est pas fourni, le reste de la chaîne est extraite.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `CStringT` qui contient une copie de la plage spécifiée des caractères. Notez que le texte retourné `CStringT` objet peut être vide.  
  
### <a name="remarks"></a>Notes  
 La fonction retourne une copie de la sous-chaîne extraite. `Mid` est similaire à la fonction Mid base (sauf que les index de base sont de base 1).  
  
 Pour les jeux de caractères multioctets (MBCS), `nCount` fait référence à chaque octet de caractère ; autrement dit, un responsable et de piste de 8 bits dans un caractères multioctets sont comptés comme deux caractères.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]  
  
##  <a name="oemtoansi"></a>  CStringT::OemToAnsi  
 Convertit tous les caractères de cette `CStringT` objet dans le jeu de caractères OEM pour le jeu de caractères ANSI.  
  
```  
void OemToAnsi();
```  
  
### <a name="remarks"></a>Notes  
 Cette fonction n’est pas disponible si `_UNICODE` est défini.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CStringT::AnsiToOem](#ansitooem).  
  
##  <a name="operator_add"></a>  CStringT::operator +  
 Concatène deux chaînes ou un caractère et une chaîne.  
  
```  
friend CStringT operator+(const CStringT& str1, const CStringT& str2);
friend CStringT operator+(const CStringT& str1, PCXSTR psz2);
friend CStringT operator+(PCXSTR psz1, const CStringT& str2,);
friend CStringT operator+(char ch1, const CStringT& str2,);
friend CStringT operator+(const CStringT& str1, char ch2);
friend CStringT operator+(const CStringT& str1, wchar_t ch2);
friend CStringT operator+(wchar_t ch1, const CStringT& str2,);
```  
  
### <a name="parameters"></a>Paramètres  
 `ch1`  
 Un caractère ANSI ou Unicode à concaténer avec une chaîne.  
  
 `ch2`  
 Un caractère ANSI ou Unicode à concaténer avec une chaîne.  
  
 `str1`  
 A `CStringT` à concaténer avec une chaîne ou un caractère.  
  
 `str2`  
 A `CStringT` à concaténer avec une chaîne ou un caractère.  
  
 `psz1`  
 Pointeur vers une chaîne se terminant par null à concaténer avec une chaîne ou un caractère.  
  
 `psz2`  
 Un pointeur vers une chaîne à concaténer avec une chaîne ou un caractère.  
  
### <a name="remarks"></a>Notes  
 Il existe sept formes de surcharge de la `CStringT::operator+` (fonction). La première version concatène deux existant `CStringT` objets. Les deux concaténer un `CStringT` objet et une chaîne se terminant par null. Les deux concaténer un `CStringT` objet et un caractère ANSI. Les deux dernières concaténer un `CStringT` objet et un caractère Unicode.  
  
> [!NOTE]
>  Bien qu’il soit possible de créer `CStringT` instances qui contiennent des caractères null incorporés, nous vous recommandons par rapport à elle. Appel de méthodes et opérateurs sur `CStringT` objets qui contiennent des caractères null incorporés peuvent produire des résultats inattendus.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]  
  
##  <a name="operator_add_eq"></a>  CStringT::operator +=  
 Concatène les caractères jusqu'à la fin de la chaîne.  
  
```  
CStringT& operator+=(const CThisSimpleString& str);

template<bool bMFCDLL>  
CStringT& operator+=(const const CSimpleStringT<BaseType, bMFCDLL>& str);

template<int t_nSize>  
CStringT& operator+=(const CStaticString<XCHAR, t_nSize>& strSrc);
CStringT& operator+=(PCXSTR pszSrc);
CStringT& operator+=(PCYSTR pszSrc);
CStringT& operator+=(char ch);
CStringT& operator+=(unsigned char ch);
CStringT& operator+=(wchar_t ch);
CStringT& operator+=(const VARIANT& var);
```  
  
### <a name="parameters"></a>Paramètres  
 str  
 Référence à un objet `CThisSimpleString`.  
  
 `bMFCDLL`  
 Valeur booléenne qui spécifie si le projet est une DLL MFC ou non.  
  
 `BaseType`  
 Le type de base de chaîne.  
  
 `var`  
 Un objet de type variant à concaténer à cette chaîne.  
  
 `ch`  
 Un caractère ANSI ou Unicode à concaténer avec une chaîne.  
  
 `pszSrc`  
 Pointeur vers la concaténation de chaîne d’origine.  
  
 `strSrc`  
 A `CStringT` à concaténer à cette chaîne.  
  
### <a name="remarks"></a>Notes  
 L’opérateur accepte un autre `CStringT` objet, un pointeur de caractère ou un caractère unique. Vous devez être conscient que les exceptions peuvent se produire lorsque vous utilisez cet opérateur de concaténation, car le nouveau stockage peut être alloué pour les caractères ajoutés à cette mémoire `CStringT` objet.  
  
 Pour plus d’informations sur `CThisSimpleString`, consultez la section Notes de [CStringT::CStringT](#cstringt).  
  
> [!NOTE]
>  Bien qu’il soit possible de créer `CStringT` instances qui contiennent des caractères null incorporés, nous vous recommandons par rapport à elle. Appel de méthodes et opérateurs sur `CStringT` objets qui contiennent des caractères null incorporés peuvent produire des résultats inattendus.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]  
  
##  <a name="operator_eq_eq"></a>  CStringT::operator ==  
 Détermine si deux chaînes sont logiquement égales.  
  
```  
friend bool operator==(const CStringT& str1, const CStringT& str2) throw();
friend bool operator==(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator==(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator==(const CStringT& str1, XCHAR ch2) throw();
friend bool operator==(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator==(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator==(XCHAR ch1, const CStringT& str2,) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `ch1`  
 Un caractère ANSI ou Unicode pour la comparaison.  
  
 `ch2`  
 Un caractère ANSI ou Unicode pour la comparaison.  
  
 `str1`  
 A `CStringT` pour la comparaison.  
  
 `str2`  
 A `CStringT` pour la comparaison.  
  
 `psz1`  
 Un pointeur vers une chaîne se terminant par null pour la comparaison.  
  
 `psz2`  
 Un pointeur vers une chaîne se terminant par null pour la comparaison.  
  
### <a name="remarks"></a>Notes  
 Teste si une chaîne ou le caractère situé à gauche est égal à une chaîne ou le caractère situé à droite et retourne TRUE ou FALSE en conséquence.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]  
  
##  <a name="operator_neq"></a>  CStringT::operator ! =  
 Détermine si deux chaînes sont logiquement pas égales.  
  
```  
friend bool operator!=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator!=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator!=(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator!=(const CStringT& str1, XCHAR ch2) throw();
friend bool operator!=(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator!=(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator!=(XCHAR ch1, const CStringT& str2,) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `ch1`  
 Un caractère ANSI ou Unicode à concaténer avec une chaîne.  
  
 `ch2`  
 Un caractère ANSI ou Unicode à concaténer avec une chaîne.  
  
 `str1`  
 A `CStringT` pour la comparaison.  
  
 `str2`  
 A `CStringT` pour la comparaison.  
  
 `psz1`  
 Un pointeur vers une chaîne se terminant par null pour la comparaison.  
  
 `psz2`  
 Un pointeur vers une chaîne se terminant par null pour la comparaison.  
  
### <a name="remarks"></a>Notes  
 Teste si une chaîne ou le caractère situé à gauche n’est pas égal à une chaîne ou le caractère situé à droite.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]  
  
##  <a name="operator_lt"></a>  CStringT::operator &lt;  
 Détermine si la chaîne sur le côté gauche de l’opérateur est inférieur à la chaîne située à droite.  
  
```  
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `str1`  
 A `CStringT` pour la comparaison.  
  
 `str2`  
 A `CStringT` pour la comparaison.  
  
 `psz1`  
 Un pointeur vers une chaîne se terminant par null pour la comparaison.  
  
 `psz2`  
 Un pointeur vers une chaîne se terminant par null pour la comparaison.  
  
### <a name="remarks"></a>Notes  
 Une comparaison lexicographique entre des chaînes, caractère par caractère jusqu'à ce que :  
  
-   Elle trouve deux caractères correspondants inégaux et le résultat de leur comparaison est considéré comme étant le résultat de la comparaison entre les chaînes.  
  
-   Elle ne trouve aucune inégalité, mais une chaîne a plus de caractères que l’autre, et la chaîne la plus courte est considérée comme inférieure à la chaîne la plus longue.  
  
-   Elle ne trouve aucune inégalité et les chaînes ont le même nombre de caractères, si bien que les chaînes sont égales.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]  
  
##  <a name="operator_gt"></a>  CStringT::operator &gt;  
 Détermine si la chaîne sur le côté gauche de l’opérateur est supérieure à la chaîne située à droite.  
  
```  
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `str1`  
 A `CStringT` pour la comparaison.  
  
 `str2`  
 A `CStringT` pour la comparaison.  
  
 `psz1`  
 Un pointeur vers une chaîne se terminant par null pour la comparaison.  
  
 `psz2`  
 Un pointeur vers une chaîne se terminant par null pour la comparaison.  
  
### <a name="remarks"></a>Notes  
 Une comparaison lexicographique entre des chaînes, caractère par caractère jusqu'à ce que :  
  
-   Elle trouve deux caractères correspondants inégaux et le résultat de leur comparaison est considéré comme étant le résultat de la comparaison entre les chaînes.  
  
-   Elle ne trouve aucune inégalité, mais une chaîne a plus de caractères que l’autre, et la chaîne la plus courte est considérée comme inférieure à la chaîne la plus longue.  
  
-   Elle ne trouve aucune inégalité et les chaînes ont le même nombre de caractères, si bien que les chaînes sont égales.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]  
  
##  <a name="operator_lt_eq"></a>  CStringT::operator &lt;=  
 Détermine si la chaîne sur le côté gauche de l’opérateur est inférieur ou égal à la chaîne située à droite.  
  
```  
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `str1`  
 A `CStringT` pour la comparaison.  
  
 `str2`  
 A `CStringT` pour la comparaison.  
  
 `psz1`  
 Un pointeur vers une chaîne se terminant par null pour la comparaison.  
  
 `psz2`  
 Un pointeur vers une chaîne se terminant par null pour la comparaison.  
  
### <a name="remarks"></a>Notes  
 Une comparaison lexicographique entre des chaînes, caractère par caractère jusqu'à ce que :  
  
-   Elle trouve deux caractères correspondants inégaux et le résultat de leur comparaison est considéré comme étant le résultat de la comparaison entre les chaînes.  
  
-   Elle ne trouve aucune inégalité, mais une chaîne a plus de caractères que l’autre, et la chaîne la plus courte est considérée comme inférieure à la chaîne la plus longue.  
  
-   Elle ne trouve aucune inégalité et les chaînes ont le même nombre de caractères, si bien que les chaînes sont égales.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]  
  
##  <a name="operator_gt_eq"></a>  CStringT::operator &gt;=  
 Détermine si la chaîne sur le côté gauche de l’opérateur est supérieur ou égal à la chaîne située à droite.  
  
```  
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `str1`  
 A `CStringT` pour la comparaison.  
  
 `str2`  
 A `CStringT` pour la comparaison.  
  
 `psz1`  
 Un pointeur vers une chaîne pour la comparaison.  
  
 `psz2`  
 Un pointeur vers une chaîne pour la comparaison.  
  
### <a name="remarks"></a>Notes  
 Une comparaison lexicographique entre des chaînes, caractère par caractère jusqu'à ce que :  
  
-   Elle trouve deux caractères correspondants inégaux et le résultat de leur comparaison est considéré comme étant le résultat de la comparaison entre les chaînes.  
  
-   Elle ne trouve aucune inégalité, mais une chaîne a plus de caractères que l’autre, et la chaîne la plus courte est considérée comme inférieure à la chaîne la plus longue.  
  
-   Elle ne trouve aucune inégalité et les chaînes ont le même nombre de caractères, si bien que les chaînes sont égales.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]  
  
##  <a name="remove"></a>  CStringT::Remove  
 Supprime toutes les instances du caractère spécifié de la chaîne.  
  
```  
int Remove(XCHAR chRemove);
```  
  
### <a name="parameters"></a>Paramètres  
 `chRemove`  
 Le caractère doit être supprimée à partir d’une chaîne.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de caractères à supprimer de la chaîne. Zéro si la chaîne n’est pas modifiée.  
  
### <a name="remarks"></a>Notes  
 Les comparaisons du caractère respectent la casse.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]  
  
##  <a name="replace"></a>  CStringT::Replace  
 Il existe deux versions de `Replace`. La première version remplace une ou plusieurs copies d’une sous-chaîne par une autre sous-chaîne. Les deux sous-chaînes sont se terminant par null. La deuxième version remplace une ou plusieurs copies d’un caractère à l’aide d’un autre caractère. Les deux versions ne fonctionne pas sur les données de caractères stockées dans `CStringT`.  
  
```  
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```  
  
### <a name="parameters"></a>Paramètres  
 `pszOld`  
 Un pointeur vers une chaîne se terminant par null à remplacer par `pszNew`.  
  
 `pszNew`  
 Un pointeur vers une chaîne se terminant par null qui remplace `pszOld`.  
  
 `chOld`  
 Le caractère à remplacer par `chNew`.  
  
 `chNew`  
 Le remplacement de caractères `chOld`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre d’instances remplacés de caractère ou sous-chaîne ou zéro si la chaîne n’est pas modifiée.  
  
### <a name="remarks"></a>Notes  
 `Replace` peut modifier la longueur de chaîne car `pszNew` et `pszOld` n’ont pas à être la même longueur, et plusieurs copies de la sous-chaîne ancien peuvent être remplacés par une nouvelle. La fonction effectue une correspondance qui respecte la casse.  
  
 Exemples de `CStringT` sont des instances `CString`, `CStringA`, et `CStringW`.  
  
 Pour `CStringA`, `Replace` fonctionne avec ANSI ou des caractères multioctets (MBCS). Pour `CStringW`, `Replace` fonctionne avec les caractères larges.  
  
 Pour `CString`, le type de données caractère est sélectionné au moment de la compilation, selon si l’une des constantes dans le tableau suivant sont définis.  
  
|Constante définie|Type de données caractère|  
|----------------------|-------------------------|  
|`_UNICODE`|Caractères larges|  
|`_MBCS`|Caractères multioctets|  
|Ni|Caractères codés sur un octet|  
|Both|Undefined|  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]  
  
##  <a name="reversefind"></a>  CStringT::ReverseFind  
 Cette recherche `CStringT` objet pour la dernière correspondance d’un caractère.  
  
```  
int ReverseFind(XCHAR ch) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `ch`  
 Caractère à rechercher.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro du caractère dans cette dernière `CStringT` objet qui correspond aux caractères demandé, ou -1 si le caractère est introuvable.  
  
### <a name="remarks"></a>Notes  
 La fonction est similaire à la fonction de l’exécution `strrchr`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]  
  
##  <a name="right"></a>  CStringT::Right  
 Extrait la dernière (autrement dit, plus à droite) `nCount` caractères à partir de ce `CStringT` de l’objet et retourne une copie de la sous-chaîne extraite.  
  
```  
CStringT Right(int nCount) const; 
```  
  
### <a name="parameters"></a>Paramètres  
 `nCount`  
 Nombre de caractères à extraire de cet objet `CStringT`.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `CStringT` qui contient une copie de la plage spécifiée des caractères. Notez que le texte retourné `CStringT` objet ne peut être vide.  
  
### <a name="remarks"></a>Notes  
 Si `nCount` dépasse la longueur de la chaîne, la chaîne entière est extraite. `Right` est similaire à la base `Right` (sauf que les index de base sont de base zéro) de la fonction.  
  
 Pour les jeux de caractères multioctets (MBCS), `nCount` fait référence à chaque octet de caractère ; autrement dit, un responsable et de piste de 8 bits dans un caractères multioctets sont comptés comme deux caractères.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]  
  
##  <a name="setsysstring"></a>  CStringT::SetSysString  
 Réalloue le `BSTR` vers lequel pointe `pbstr` et copie le contenu de la `CStringT` objet, y compris les `NULL` caractères.  
  
```  
BSTR SetSysString(BSTR* pbstr) const; 
```  
  
### <a name="parameters"></a>Paramètres  
 `pbstr`  
 Pointeur vers une chaîne de caractères.  
  
### <a name="return-value"></a>Valeur de retour  
 La nouvelle chaîne.  
  
### <a name="remarks"></a>Notes  
 En fonction du contenu de la `CStringT` objet, la valeur de la `BSTR` référencé par `pbstr` peut changer. La fonction lève une `CMemoryException` en cas de mémoire insuffisante.  
  
 Cette fonction est normalement utilisée pour modifier la valeur de chaînes passé par référence pour l’automatisation.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]  
  
##  <a name="spanexcluding"></a>  CStringT::SpanExcluding  
 Extrait les caractères de la chaîne, en commençant par le premier caractère qui ne sont pas dans le jeu de caractères identifié par `pszCharSet`.  
  
```  
CStringT SpanExcluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>Paramètres  
 `pszCharSet`  
 Une chaîne est interprétée comme un jeu de caractères.  
  
### <a name="return-value"></a>Valeur de retour  
 Une sous-chaîne qui contient des caractères qui ne sont pas dans la chaîne `pszCharSet`, commençant par le premier caractère dans la chaîne et se terminant par le premier caractère trouvé dans la chaîne se trouve également dans `pszCharSet` (autrement dit, en commençant par le premier caractère dans le chaîne et jusqu'à excluant le premier caractère dans la chaîne est trouvée `pszCharSet`). Elle retourne la chaîne entière si aucun caractère dans `pszCharSet` se trouve dans la chaîne.  
  
### <a name="remarks"></a>Notes  
 `SpanExcluding` extrait et retourne tous les caractères qui précède la première occurrence d’un caractère à partir de `pszCharSet` (en d’autres termes, le caractère à partir de `pszCharSet` et tous les caractères suivant dans la chaîne, ne sont pas retournés). Si aucun caractère de `pszCharSet` est trouvé dans la chaîne, puis `SpanExcluding` retourne la chaîne entière.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]  
  
##  <a name="spanincluding"></a>  CStringT::SpanIncluding  
 Extrait les caractères de la chaîne, en commençant par le premier caractère, qui se trouvent dans le jeu de caractères identifié par `pszCharSet`.  
  
```  
CStringT SpanIncluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>Paramètres  
 `pszCharSet`  
 Une chaîne est interprétée comme un jeu de caractères.  
  
### <a name="return-value"></a>Valeur de retour  
 Une sous-chaîne qui contienne des caractères dans la chaîne qui se trouvent dans `pszCharSet`, commençant par le premier caractère dans la chaîne et de fin quand un caractère est trouvé dans la chaîne qui n’est pas `pszCharSet`. `SpanIncluding` Retourne une sous-chaîne vide si le premier caractère dans la chaîne n’est pas dans le jeu spécifié.  
  
### <a name="remarks"></a>Notes  
 Si le premier caractère de la chaîne n’est pas, dans le jeu de caractères `SpanIncluding` retourne une chaîne vide. Sinon, elle retourne une séquence de caractères consécutifs qui se trouvent dans le jeu.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]  
  
##  <a name="tokenize"></a>  CStringT::Tokenize  
 Recherche le jeton suivant dans une chaîne cible  
  
```  
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const; 
```  
  
### <a name="parameters"></a>Paramètres  
 `pszTokens`  
 Chaîne contenant des séparateurs de jetons. L’ordre de ces délimiteurs n’est pas important.  
  
 `iStart`  
 Index de base zéro pour commencer la recherche.  
  
### <a name="return-value"></a>Valeur de retour  
 A `CStringT` objet contenant la valeur du jeton en cours.  
  
### <a name="remarks"></a>Notes  
 Le `Tokenize` fonction recherche le jeton suivant dans la chaîne cible. Le jeu de caractères dans `pszTokens` spécifie des délimiteurs possibles du jeton doit être trouvé. Sur chaque appel à `Tokenize` la fonction commence à `iStart`, ignore les délimiteurs de début et retourne un `CStringT` objet contenant le jeton actuel, qui est la chaîne de caractères jusqu’au prochain caractère de délimiteur. La valeur de `iStart` est mis à jour à la position qui suit le caractère délimiteur de fin, ou -1 si la fin de la chaîne a été atteinte. Plus de jetons peuvent être classées en dehors du reste de la chaîne cible par une série d’appels à `Tokenize`, à l’aide `iStart` pour effectuer le suivi de l’emplacement dans la chaîne de jeton suivant doit être lu. Lorsqu’il n’y a aucuns plus de jetons de la fonction retourne une chaîne vide et `iStart` a la valeur -1.  
  
 Contrairement à la bibliothèque CRT marquer des fonctions telles que [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md), `Tokenize` ne modifie pas la chaîne cible.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]  
  
### <a name="remarks"></a>Notes  
 La sortie de cet exemple est la suivante :  
  
 `Resulting Token: First`  
  
 `Resulting Token: Second`  
  
 `Resulting Token: Third`  
  
##  <a name="trim"></a>  CStringT::Trim  
 Supprime les premiers et derniers caractères de la chaîne.  
  
```  
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```  
  
### <a name="parameters"></a>Paramètres  
 `chTarget`  
 Le caractère de la cible à découper.  
  
 `pszTargets`  
 Un pointeur vers une chaîne contenant les caractères de la cible à découper. Tous les premiers et derniers occurrences des caractères contenus dans `pszTarget` seront effacées du `CStringT` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la chaîne découpée.  
  
### <a name="remarks"></a>Notes  
 Supprime toutes les occurrences de début et de fin de l’une des opérations suivantes :  
  
-   Le caractère spécifié par `chTarget.`  
  
-   Tous les caractères ont été trouvés dans la chaîne spécifiée par `pszTargets.`  
  
-   Espace blanc.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]  
  
### <a name="remarks"></a>Notes  
 La sortie de cet exemple est la suivante :  
  
 `Before: "******Soccer is best, but liquor is quicker!!!!!"`  
  
 `After : "Soccer is best, but liquor is quicker"`  
  
##  <a name="trimleft"></a>  CStringT::TrimLeft  
 Supprime les caractères de début de la chaîne.  
  
```  
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```  
  
### <a name="parameters"></a>Paramètres  
 `chTarget`  
 Le caractère de la cible à découper.  
  
 `pszTargets`  
 Un pointeur vers une chaîne contenant les caractères de la cible à découper. Toutes les occurrences situées au début de caractères dans `pszTarget` seront effacées du `CStringT` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Chaîne découpée résultante.  
  
### <a name="remarks"></a>Notes  
 Supprime toutes les occurrences de début et de fin de l’une des opérations suivantes :  
  
-   Le caractère spécifié par `chTarget.`  
  
-   Tous les caractères ont été trouvés dans la chaîne spécifiée par `pszTargets.`  
  
-   Espace blanc.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]  
  
##  <a name="trimright"></a>  CStringT::TrimRight  
 Supprime les caractères de la chaîne.  
  
```  
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```  
  
### <a name="parameters"></a>Paramètres  
 `chTarget`  
 Le caractère de la cible à découper.  
  
 `pszTargets`  
 Un pointeur vers une chaîne contenant les caractères de la cible à découper. Toutes les occurrences des caractères de fin `pszTarget` seront effacées du `CStringT` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le `CStringT` objet qui contient la chaîne découpée.  
  
### <a name="remarks"></a>Notes  
 Supprime les occurrences de l’une des opérations suivantes :  
  
-   Le caractère spécifié par `chTarget.`  
  
-   Tous les caractères ont été trouvés dans la chaîne spécifiée par `pszTargets.`  
  
-   Espace blanc.  
  
 Le `CStringT& TrimRight(XCHAR chTarget)` version accepte un paramètre de caractère et supprime toutes les copies de ce caractère à partir de la fin de `CStringT` données de chaîne. Il démarre à partir de la fin de la chaîne et fonctionne vers l’avant. Il s’arrête lorsqu’elle détecte un caractère différent ou lorsque `CSTringT` suffisamment de données de type caractère.  
  
 Le `CStringT& TrimRight(PCXSTR pszTargets)` version accepte une chaîne se terminant par null qui contient tous les différents caractères à rechercher. Il supprime toutes les copies de ces caractères dans le `CStringT` objet. Il commence à la fin de la chaîne et fonctionne vers l’avant. Il s’arrête lorsqu’elle détecte un caractère qui n’est pas dans la chaîne cible, ou lorsque `CStringT` suffisamment de données de type caractère. Il ne tente pas de correspondent à la chaîne entière cible à une sous-chaîne à la fin de `CStringT`.  
  
 Le `CStringT& TrimRight()` version ne requiert aucun paramètre. Il supprime tout espace blanc de fin de la fin de la `CStringT` chaîne. Caractères d’espace peuvent être sauts de ligne, des espaces ou des onglets.  
  
-  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes de partagées ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)   
 [CSimpleStringT, classe](../../atl-mfc-shared/reference/csimplestringt-class.md)


