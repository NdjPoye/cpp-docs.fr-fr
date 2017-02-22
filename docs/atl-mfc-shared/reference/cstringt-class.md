---
title: "CStringT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CString"
  - "CStringT"
  - "ATL::CStringT"
  - "ATL.CStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringT class"
  - "shared classes, CStringT"
  - "chaînes (C++), dans ATL"
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 34
---
# CStringT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente un objet d' `CStringT` .  
  
## Syntaxe  
  
```  
  
      template< typename   
      BaseType  
      , class   
      StringTraits  
       >  
class CStringT :   
public CSimpleStringT<   BaseType,   _CSTRING_IMPL_::_MFCDLLTraitsCheck<      BaseType,      StringTraits   >   ::c_bIsMFCDLLTraits>  
```  
  
#### Paramètres  
 `BaseType`  
 Le type de caractère de la classe de chaîne.  Il peut s'agir de l'une des valeurs suivantes :  
  
-   `char` \(pour les chaînes de caractères ANSI\).  
  
-   `wchar_t` \(pour les chaînes de caractères Unicode\).  
  
-   **TCHAR** \(pour ANSI et des chaînes de caractères Unicode\).  
  
 `StringTraits`  
 Détermine si la classe de chaîne a besoin de la prise en charge de la bibliothèque de \(CRT\) de runtime C et l'emplacement des ressources de type chaîne localisées.  Il peut s'agir de l'une des valeurs suivantes :  
  
-   **Wchar\_t de strtraitatl\<** &#124; `char` &#124; **TCHAR, de chtraitscrt\< wchar\_t** &#124; `char` &#124; **TCHAR \> \>**  
  
     La classe nécessite la prise en charge et les recherches CRT des chaînes de ressources dans le package spécifié par `m_hInstResource` \(membre de la classe du package de l'utilisation\).  
  
-   **Wchar\_t de strtraitatl\<** &#124; `char` &#124; **TCHAR, de chtraitsos\< wchar\_t** &#124; `char` &#124; **TCHAR \> \>**  
  
     La classe ne requiert pas en charge les recherches CRT des chaînes de ressources dans le package spécifié par `m_hInstResource` \(membre de la classe du package de l'utilisation\).  
  
-   **Wchar\_t de strtraitmfc\<** &#124; `char` &#124; **TCHAR, de chtraitscrt\< wchar\_t** &#124; `char` &#124; **TCHAR \> \>**  
  
     La classe nécessite la prise en charge et les recherches CRT des chaînes de ressource à l'aide de l'algorithme de recherche MFC standard.  
  
-   **Wchar\_t de strtraitmfc\<** &#124; `char` &#124; **TCHAR, de chtraitsos\< wchar\_t** &#124; `char` &#124; **TCHAR \> \>**  
  
     La classe ne requiert pas en charge les recherches CRT des chaînes de ressource à l'aide de l'algorithme de recherche MFC standard.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CStringT::CStringT](../Topic/CStringT::CStringT.md)|Construit un objet d' `CStringT` de plusieurs façons.|  
|[CStringT::~CStringT](../Topic/CStringT::~CStringT.md)|Détruit un objet `CStringT`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md)|Alloue `BSTR` des données d' `CStringT` .|  
|[CStringT::AnsiToOem](../Topic/CStringT::AnsiToOem.md)|Effectue une conversion sur place du jeu de caractères ANSI au jeu de caractères OEM.|  
|[CStringT::AppendFormat](../Topic/CStringT::AppendFormat.md)|Appends a mis en forme des données à un objet existant d' `CStringT` .|  
|[CStringT::Collate](../Topic/CStringT::Collate.md)|Compare deux chaînes \(respectant la casse, des informations spécifiques aux paramètres régionaux de l'utilise\).|  
|[CStringT::CollateNoCase](../Topic/CStringT::CollateNoCase.md)|Compare deux chaînes \(respectant la casse, des informations spécifiques aux paramètres régionaux de l'utilise\).|  
|[CStringT::Compare](../Topic/CStringT::Compare.md)|Compare deux chaînes \(respectant la casse\).|  
|[CStringT::CompareNoCase](../Topic/CStringT::CompareNoCase.md)|Compare deux chaînes \(respectant la casse\).|  
|[CStringT::Delete](../Topic/CStringT::Delete.md)|Supprime le caractère ou des caractères d'une chaîne.|  
|[CStringT::Find](../Topic/CStringT::Find.md)|Recherche un caractère ou une sous\-chaîne dans une chaîne plus grande.|  
|[CStringT::FindOneOf](../Topic/CStringT::FindOneOf.md)|Recherche le premier caractère correspondant d'un jeu.|  
|[CStringT::Format](../Topic/CStringT::Format.md)|Met en forme la chaîne comme le fait `sprintf` .|  
|[CStringT::FormatMessage](../Topic/CStringT::FormatMessage.md)|Met en forme une chaîne de message.|  
|[CStringT::FormatMessageV](../Topic/CStringT::FormatMessageV.md)|Met en forme une chaîne de message à l'aide d'une liste d'arguments variable.|  
|[CStringT::FormatV](../Topic/CStringT::FormatV.md)|Met en forme la chaîne à l'aide d'une liste d'arguments variable.|  
|[CStringT::GetEnvironmentVariable](../Topic/CStringT::GetEnvironmentVariable.md)|Définit la chaîne à la valeur de la variable d'environnement spécifiée.|  
|[CStringT::Insert](../Topic/CStringT::Insert.md)|Insère un caractère unique ou une sous\-chaîne à l'index donné dans la chaîne.|  
|[CStringT::Left](../Topic/CStringT::Left.md)|Récupère le côté gauche d'une chaîne.|  
|[CStringT::LoadString](../Topic/CStringT::LoadString.md)|Charge un objet existant d' `CStringT` d'une ressource windows.|  
|[CStringT::MakeLower](../Topic/CStringT::MakeLower.md)|Convertit tous les caractères dans cette chaîne en minuscules.|  
|[CStringT::MakeReverse](../Topic/CStringT::MakeReverse.md)|Inverse la chaîne.|  
|[CStringT::MakeUpper](../Topic/CStringT::MakeUpper.md)|Convertit tous les caractères dans cette chaîne en majuscules.|  
|[CStringT::Mid](../Topic/CStringT::Mid.md)|Extrait la partie moyenne d'une chaîne.|  
|[CStringT::OemToAnsi](../Topic/CStringT::OemToAnsi.md)|Effectue une conversion sur place du jeu de caractères OEM au jeu de caractères ANSI.|  
|[CStringT::Remove](../Topic/CStringT::Remove.md)|A indiqué supprime les caractères d'une chaîne.|  
|[CStringT::Replace](../Topic/CStringT::Replace.md)|Replaces a indiqué des caractères avec d'autres caractères.|  
|[CStringT::ReverseFind](../Topic/CStringT::ReverseFind.md)|Recherche un caractère dans une chaîne plus grande ; commence à partir de la fin.|  
|[CStringT::Right](../Topic/CStringT::Right.md)|Extrait une bonne partie d'une chaîne.|  
|[CStringT::SetSysString](../Topic/CStringT::SetSysString.md)|Définit un objet existant d' `BSTR` avec les données d'un objet d' `CStringT` .|  
|[CStringT::SpanExcluding](../Topic/CStringT::SpanExcluding.md)|Récupère les caractères de la chaîne, en commençant par le premier caractère, qui ne figurent pas dans le jeu de caractères reconnus par `pszCharSet`.|  
|[CStringT::SpanIncluding](../Topic/CStringT::SpanIncluding.md)|Extrait une sous\-chaîne qui contient uniquement des caractères dans un jeu.|  
|[CStringT::Tokenize](../Topic/CStringT::Tokenize.md)|Le spécifiées par récupérés à une chaîne cible.|  
|[CStringT::Trim](../Topic/CStringT::Trim.md)|Supprime tous les caractères de début et de fin de l'espace blanc de la chaîne.|  
|[CStringT::TrimLeft](../Topic/CStringT::TrimLeft.md)|Équilibres ce qui entraîne des caractères d'espace blanc de la chaîne.|  
|[CStringT::TrimRight](../Topic/CStringT::TrimRight.md)|Équilibres traînant des caractères d'espace blanc de la chaîne.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[CStringT::operator \=](../Topic/CStringT::operator%20=.md)|Assigne une valeur à un objet d' `CStringT` .|  
|[CStringT::operator \+](../Topic/CStringT::operator%20+.md)|Concatène deux chaînes ou un caractère et une chaîne.|  
|[CStringT::operator \+\=](../Topic/CStringT::operator%20+=.md)|Concatène une nouvelle chaîne à la fin d'une chaîne existante.|  
|[CStringT::operator \=\=](../Topic/CStringT::operator%20==.md)|Détermine si deux chaînes sont logiquement égales.|  
|[CStringT::operator \!\=](../Topic/CStringT::operator%20!=.md)|Détermine si deux chaînes sont logiquement pas égales.|  
|[CStringT::operator \<](../Topic/CStringT::operator%20%3C.md)|Détermine si la chaîne sur le côté gauche de l'opérateur est moins qu'à la chaîne du côté droit.|  
|[CStringT::operator \>](../Topic/CStringT::operator%20%3E.md)|Détermine si la chaîne sur le côté gauche de l'opérateur est supérieure à la chaîne du côté droit.|  
|[CStringT::operator \<\=](../Topic/CStringT::operator%20%3C=.md)|Détermine si la chaîne sur le côté gauche de l'opérateur est inférieure ou égale à la chaîne du côté droit.|  
|[CStringT::operator \>\=](../Topic/CStringT::operator%20%3E=.md)|Détermine si la chaîne sur le côté gauche de l'opérateur est supérieur ou égal à la chaîne du côté droit.|  
  
## Notes  
 `CStringT` hérite de [classe de CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md).  La fonctionnalité avancée, telle que la manipulation de caractère, ordonner, et rechercher, est implémentée par `CStringT`.  
  
> [!NOTE]
>  Les objets d'`CStringT` sont capables de lever des exceptions.  Cela se produit lorsque les opérations d'objet d' `CStringT` mémoire insuffisante pour une raison quelconque.  
  
 Un objet d' `CStringT` se compose d'une séquence de longueur variable de caractères.  `CStringT` fournit des fonctions et des opérateurs de l'utilisation de la syntaxe semblable à celle de base.  La concaténation et les opérateurs de comparaison, ainsi que la gestion de la mémoire simplifiée, facilitent les objets d' `CStringT` pour utiliser que les tableaux de caractères ordinaires.  
  
> [!NOTE]
>  Bien qu'il soit possible de créer des instances d' `CStringT` qui contiennent des caractères Null incorporés, nous recommandons sur elles.  Les méthodes d'appel et les opérateurs sur les objets d' `CStringT` qui contiennent des caractères Null incorporés peuvent produire des résultats inattendus.  
  
 En utilisant différentes combinaisons de paramètres d' `BaseType` et d' `StringTraits` , les objets d' `CStringT` peuvent provenir dans les types suivants, qui sont ont été intégrés par les bibliothèques ATL.  
  
 Si vous utilisez dans une application ATL :  
  
 `CString`, `CStringA`, et `CStringW` sont exportées de la DLL MFC \(MFC90.DLL\), jamais des DLL d'utilisateur.  Cela permet d'empêcher d'être `CStringT` de multiplier défini.  
  
> [!NOTE]
>  Si vous rencontriez des erreurs d'éditeur de liens en exportant `CString`classe dérivée d'une DLL d'extension MFC dans Visual C\+\+ .NET 2002 et avez appliqué la solution de contournement décrite dans l'article de la Base de connaissances, « liant des erreurs lorsque vous importez des classes Dérivées CString\- » \(Q309801\), vous devez supprimer le code de solution, car cela a été résolu dans Visual C\+\+ .NET 2003.  Vous trouverez les articles de la Base de connaissances sur le CD\-ROM de MSDN Library ou à l'adresse [http:\/\/support.microsoft.com\/default.aspx](http://support.microsoft.com/default.aspx).  
  
 Les types de chaînes suivants sont disponibles dans des applications basées sur MFC :  
  
|Type de CStringT|Déclaration|  
|----------------------|-----------------|  
|`CStringA`|Un type de caractère ANSI chaîne avec la prise en charge du CRT.|  
|`CStringW`|Un type de caractère Unicode chaîne avec la prise en charge du CRT.|  
|`CString`|ANSI et types de caractères Unicode avec la prise en charge du CRT.|  
  
 Les types de chaînes suivants sont disponibles dans les projets dans laquelle **ATL\_CSTRING\_NO\_CRT** est définie :  
  
|Type de CStringT|Déclaration|  
|----------------------|-----------------|  
|**CAtlStringA**|Un type de caractère ANSI chaîne sans prise en charge du CRT.|  
|**CAtlStringW**|Un type de caractère Unicode chaîne sans prise en charge du CRT.|  
|**CAtlString**|ANSI et types de caractères Unicode sans prise en charge du CRT.|  
  
 Les types de chaînes suivants sont disponibles dans les projets dans laquelle **ATL\_CSTRING\_NO\_CRT** n'est pas définie :  
  
|Type de CStringT|Déclaration|  
|----------------------|-----------------|  
|**CAtlStringA**|Un type de caractère ANSI chaîne avec la prise en charge du CRT.|  
|**CAtlStringW**|Un type de caractère Unicode chaîne avec la prise en charge du CRT.|  
|**CAtlString**|ANSI et types de caractères Unicode avec la prise en charge du CRT.|  
  
 Les objets d'`CString` ont également les caractéristiques suivantes :  
  
-   Les objets d'`CStringT` peuvent développer à la suite de opérations de concaténation.  
  
-   Les objets d'`CStringT` suivent la sémantique « value ». Pensez à un objet d' `CStringT` comme une chaîne réelle, et non en tant que pointeur vers une chaîne.  
  
-   Vous pouvez substituer librement des objets d' `CStringT` pour les arguments de fonction d' `PCXSTR` .  
  
-   Gestion de la mémoire personnalisée pour les mémoires tampon de chaîne.  Pour plus d'informations, consultez [gestion de la mémoire et CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## CStringT a intégré des types  
 Étant donné qu' `CStringT` utilise un argument template pour définir le type de caractère \( [wchar\_t](../../c-runtime-library/standard-types.md) ou [char](../../c-runtime-library/standard-types.md)\) pris en charge, des types de paramètres de méthode peuvent être compliqués parfois.  Pour simplifier ce problème, un ensemble de types prédéfinis est défini et utilisé dans toute la classe d' `CStringT` .  Le tableau suivant répertorie les différents types :  
  
|Nom|Description|  
|---------|-----------------|  
|`XCHAR`|Un caractère unique \( `wchar_t` ou `char`\) avec le même type de caractère que l'objet d' `CStringT` .|  
|**YCHAR**|Un caractère unique \( `wchar_t` ou `char`\) avec le type de caractère opposé en tant qu'objet d' `CStringT` .|  
|`PXSTR`|Un pointeur vers une chaîne de caractères \( `wchar_t` ou `char`\) avec le même type de caractère que l'objet d' `CStringT` .|  
|**PYSTR**|Un pointeur vers une chaîne de caractères \( `wchar_t` ou `char`\) avec le type de caractère opposé en tant qu'objet d' `CStringT` .|  
|`PCXSTR`|Un pointeur vers une chaîne de caractères de **const** \( `wchar_t` ou `char`\) avec le même type de caractère que l'objet d' `CStringT` .|  
|**PCYSTR**|Un pointeur vers une chaîne de caractères de **const** \( `wchar_t` ou `char`\) avec le type de caractère opposé en tant qu'objet d' `CStringT` .|  
  
> [!NOTE]
>  Le code que les méthodes non documentées précédemment utilisées de `CString` \(tel qu' **AssignCopy**\) doivent être remplacées par le code qui utilise les méthodes documentées suivantes pour `CStringT` \(tel qu' `GetBuffer` ou `ReleaseBuffer`\).  Ces méthodes sont héritées d' `CSimpleStringT`.  
  
## Hiérarchie d'héritage  
 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)  
  
 `CStringT`  
  
## Configuration requise  
  
|Header|À utiliser pour|  
|------------|---------------------|  
|cstringt.h|Objets String réservés aux MFC|  
|atlstr.h|Objets String non\-MFC|  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)   
 [CSimpleStringT Class](../../atl-mfc-shared/reference/csimplestringt-class.md)