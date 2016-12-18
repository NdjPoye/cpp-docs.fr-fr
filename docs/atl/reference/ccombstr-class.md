---
title: "Classe CComBSTR | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComBSTR"
  - "CComBSTR"
  - "ATL.CComBSTR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSTR, wrapper"
  - "CComBSTR"
  - "classe CComBSTR"
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CComBSTR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe est un wrapper pour `BSTR`S.  
  
## Syntaxe  
  
```  
  
class CComBSTR  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComBSTR::CComBSTR](../Topic/CComBSTR::CComBSTR.md)|Constructeur.|  
|[CComBSTR::~CComBSTR](../Topic/CComBSTR::~CComBSTR.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComBSTR::Append](../Topic/CComBSTR::Append.md)|Ajoute une chaîne à `m_str`.|  
|[CComBSTR::AppendBSTR](../Topic/CComBSTR::AppendBSTR.md)|Ajoute `BSTR` à `m_str`.|  
|[CComBSTR::AppendBytes](../Topic/CComBSTR::AppendBytes.md)|Ajoute un nombre d'octets spécifié à `m_str`.|  
|[CComBSTR::ArrayToBSTR](../Topic/CComBSTR::ArrayToBSTR.md)|Crée `BSTR` du premier caractère de chaque élément dans un safearray et l'attache à l'objet d' `CComBSTR` .|  
|[CComBSTR::AssignBSTR](../Topic/CComBSTR::AssignBSTR.md)|Assigne `BSTR` à `m_str`.|  
|[CComBSTR::Attach](../Topic/CComBSTR::Attach.md)|Joint `BSTR` à l'objet d' `CComBSTR` .|  
|[CComBSTR::BSTRToArray](../Topic/CComBSTR::BSTRToArray.md)|Crée un safearray unidimensionnel de base zéro, où chaque élément du tableau est un caractère de l'objet d' `CComBSTR` .|  
|[CComBSTR::ByteLength](../Topic/CComBSTR::ByteLength.md)|Retourne la longueur d' `m_str` en octets.|  
|[CComBSTR::Copy](../Topic/CComBSTR::Copy.md)|Retourne une copie d' `m_str`.|  
|[CComBSTR::CopyTo](../Topic/CComBSTR::CopyTo.md)|Retourne une copie d' `m_str` via un paramètre de **\[out\]**|  
|[CComBSTR::Detach](../Topic/CComBSTR::Detach.md)|Détache `m_str` de l'objet d' `CComBSTR` .|  
|[CComBSTR::Empty](../Topic/CComBSTR::Empty.md)|Libère `m_str`.|  
|[CComBSTR::Length](../Topic/CComBSTR::Length.md)|Retourne la longueur d' `m_str`.|  
|[CComBSTR::LoadString](../Topic/CComBSTR::LoadString.md)|Charge une ressource de type chaîne.|  
|[CComBSTR::ReadFromStream](../Topic/CComBSTR::ReadFromStream.md)|Charge un objet d' `BSTR` d'un flux.|  
|[CComBSTR::ToLower](../Topic/CComBSTR::ToLower.md)|Convertit la chaîne en minuscules.|  
|[CComBSTR::ToUpper](../Topic/CComBSTR::ToUpper.md)|Convertit la chaîne en majuscules.|  
|[CComBSTR::WriteToStream](../Topic/CComBSTR::WriteToStream.md)|Enregistre `m_str` dans un flux.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComBSTR::operator BSTR](../Topic/CComBSTR::operator%20BSTR.md)|Effectue un objet d' `CComBSTR` à `BSTR`.|  
|[CComBSTR::operator \!](../Topic/CComBSTR::operator%20!.md)|Retourne `true` ou `false`, selon que `m_str`est `NULL`.|  
|[CComBSTR::operator \!\=](../Topic/CComBSTR::operator%20!=.md)|Compare `CComBSTR` avec une chaîne.|  
|[CComBSTR::operator &](../Topic/CComBSTR::operator%20&.md)|Retourne l'adresse d' `m_str`.|  
|[CComBSTR::operator \+\=](../Topic/CComBSTR::operator%20+=.md)|Ajoute `CComBSTR` à l'objet.|  
|[CComBSTR::operator \<](../Topic/CComBSTR::operator%20%3C.md)|Compare `CComBSTR` avec une chaîne.|  
|[CComBSTR::operator \=](../Topic/CComBSTR::operator%20=.md)|Assigne une valeur à `m_str`.|  
|[CComBSTR::operator \=\=](../Topic/CComBSTR::operator%20==.md)|Compare `CComBSTR` avec une chaîne.|  
|[CComBSTR::operator \>](../Topic/CComBSTR::operator%20%3E.md)|Compare `CComBSTR` avec une chaîne.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComBSTR::m\_str](../Topic/CComBSTR::m_str.md)|Contient `BSTR` associé à l'objet d' `CComBSTR` .|  
  
## Notes  
 La classe d' `CComBSTR` est un wrapper pour `BSTR`s, qui sont des chaînes longueur\- préfixées.  La longueur est stockée en tant qu'entier à l'emplacement mémoire précédant les données dans la chaîne.  
  
 [BSTR](http://msdn.microsoft.com/fr-fr/1b2d7d2c-47af-4389-a6b6-b01b7e915228) est se terminant par null après le dernier caractère compté mais peut également contenir des caractères Null incorporés dans la chaîne.  La longueur de chaîne n'est déterminée par le nombre de caractères, pas le premier caractère Null.  
  
> [!NOTE]
>  La classe d' `CComBSTR` fournit plusieurs membres \(constructeurs, opérateurs d'assignation, et opérateurs de comparaison\) qui prennent des chaînes ANSI ou Unicode comme arguments.  Les versions ANSI de ces fonctions sont moins efficace que leurs équivalents Unicode parce que les chaînes Unicode temporaires sont souvent créées en interne.  Pour des raisons d'efficacité, utilisez les versions Unicode lorsque cela est possible.  
  
> [!NOTE]
>  En raison de le comportement amélioré de recherche implémenté dans Visual Studio .NET, le code comme `bstr = L"String2" + bstr;`, qui peut avoir compilé dans les versions précédentes, doit être implémenté comme `bstr = CStringW(L"String2") + bstr`.  
  
 Pour une liste d'avertissements à l'aide de `CComBSTR`, consultez [programmation avec CComBSTR](../../atl/programming-with-ccombstr-atl.md).  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)   
 [ATL and MFC String Conversion Macros](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md)