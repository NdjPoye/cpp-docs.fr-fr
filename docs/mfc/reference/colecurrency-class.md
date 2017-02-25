---
title: "COleCurrency Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CURRENCY"
  - "COleCurrency"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleCurrency class"
  - "CURRENCY"
  - "fixed-point numbers"
  - "nombres, fixed-point"
ms.assetid: 3a36e345-303f-46fb-a57c-858274378a8d
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleCurrency Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule le type de données d' `CURRENCY` OLE automation de.  
  
## Syntaxe  
  
```  
class COleCurrency  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleCurrency::COleCurrency](../Topic/COleCurrency::COleCurrency.md)|Construit un objet `COleCurrency`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleCurrency::Format](../Topic/COleCurrency::Format.md)|Génère une représentation sous forme de chaîne mise en forme d'un objet d' `COleCurrency` .|  
|[COleCurrency::GetStatus](../Topic/COleCurrency::GetStatus.md)|Obtient l'état \(validité\) de cet objet d' `COleCurrency` .|  
|[COleCurrency::ParseCurrency](../Topic/COleCurrency::ParseCurrency.md)|Lit une valeur monétaire d'une chaîne et définit la valeur d' `COleCurrency`.|  
|[COleCurrency::SetCurrency](../Topic/COleCurrency::SetCurrency.md)|Définit la valeur de cet objet d' `COleCurrency` .|  
|[COleCurrency::SetStatus](../Topic/COleCurrency::SetStatus.md)|Définit le mode \(validité\) pour cet objet d' `COleCurrency` .|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[opérateur \=](../Topic/COleCurrency::operator%20=.md)|Copie une valeur d' `COleCurrency` .|  
|[opérateur \+, \-](../Topic/COleCurrency::operator%20+,%20-.md)|Ajoute, soustrait, et signe de modifications des valeurs d' `COleCurrency` .|  
|[opérateur \+, \- \=](../Topic/COleCurrency::operator%20+=,%20-=.md)|Ajoute et soustrait une valeur d' `COleCurrency` de cet objet d' `COleCurrency` .|  
|[opérateur \*, ou](../Topic/COleCurrency::operator%20*,%20-.md)|Mesure une valeur d' `COleCurrency` par une valeur entière.|  
|[\*\= d'opérateur,\/\=](../Topic/COleCurrency::operator%20*=,%20-=.md)|Mesure cette valeur d' `COleCurrency` par une valeur entière.|  
|[opérateur \<\<](../Topic/COleCurrency::operator%20%3C%3C,%20%3E%3E.md)|Affiche une valeur d' `COleCurrency` à `CArchive` ou à `CDumpContext`.|  
|[opérateur \>\>](../Topic/COleCurrency::operator%20%3C%3C,%20%3E%3E.md)|Entre un objet d' `COleCurrency` d' `CArchive`.|  
|[CURRENCY d'opérateur](../Topic/COleCurrency::operator%20CURRENCY.md)|Convertit une valeur d' `COleCurrency` dans **CURRENCY**.|  
|[\=\= d'opérateur, \<, \<\=, etc..](../Topic/COleCurrency%20Relational%20Operators.md)|Compare deux valeurs d' `COleCurrency` .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleCurrency::m\_cur](../Topic/COleCurrency::m_cur.md)|Contient **CURRENCY** sous\-jacent pour cet objet d' `COleCurrency` .|  
|[COleCurrency::m\_status](../Topic/COleCurrency::m_status.md)|Contient l'état de cet objet d' `COleCurrency` .|  
  
## Notes  
 **COleCurrency** n'a pas de classe de base.  
  
 **CURRENCY** est implémenté comme 8 octet, valeur entière de two's\-complément mise à l'échelle par 10.000.  Cela donne un nombre à virgule fixe à 15 chiffres à gauche de la virgule décimale et 4 chiffres à droite.  Le type de données de **CURRENCY** est très utile pour les calculs qui impliquent l'argent, ou pour tout calcul à virgule fixe où l'exactitude est important.  Il est l'un des types possibles pour le type de données d' `VARIANT` OLE automation de.  
  
 **COleCurrency** implémente également des opérations arithmétiques de base pour ce type à virgule fixe.  Les opérations prises en charge ont été sélectionnées pour vérifier les erreurs d'arrondi qui se produisent pendant des calculs à virgule fixe.  
  
## Hiérarchie d'héritage  
 `COleCurrency`  
  
## Configuration requise  
 **Header:** afxdisp.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleVariant Class](../../mfc/reference/colevariant-class.md)