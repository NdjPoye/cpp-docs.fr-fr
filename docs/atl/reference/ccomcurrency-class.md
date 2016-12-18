---
title: "CComCurrency Class | Microsoft Docs"
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
  - "CComCurrency"
  - "ATL.CComCurrency"
  - "ATL::CComCurrency"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCurrency class"
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComCurrency Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComCurrency` a des méthodes et des opérateurs pour créer et gérer un objet CURRENCY.  
  
## Syntaxe  
  
```  
  
class CComCurrency  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCurrency::CComCurrency](../Topic/CComCurrency::CComCurrency.md)|Constructeur d'un objet `CComCurrency`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCurrency::GetCurrencyPtr](../Topic/CComCurrency::GetCurrencyPtr.md)|Retourne l'adresse d'un membre de données `m_currency`.|  
|[CComCurrency::GetFraction](../Topic/CComCurrency::GetFraction.md)|Appelez cette méthode pour retourner la partie fractionnaire d'un objet `CComCurrency`.|  
|[CComCurrency::GetInteger](../Topic/CComCurrency::GetInteger.md)|Appelez cette méthode pour retourner la partie entière d'un objet `CComCurrency`.|  
|[CComCurrency::Round](../Topic/CComCurrency::Round.md)|Appelez cette méthode pour arrondir un objet `CComCurrency` à l'entier le plus proche.|  
|[CComCurrency::SetFraction](../Topic/CComCurrency::SetFraction.md)|Appelez cette méthode pour définir la partie fractionnaire d'un objet `CComCurrency`.|  
|[CComCurrency::SetInteger](../Topic/CComCurrency::SetInteger.md)|Appelez cette méthode pour définir la partie entière d'un objet `CComCurrency`.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCurrency::operator \-](../Topic/CComCurrency::operator%20-2.md)|Cet opérateur permet d'effectuer une soustraction sur un objet `CComCurrency`.|  
|[CComCurrency::operator \!\=](../Topic/CComCurrency::operator%20!=.md)|Compare deux objets `CComCurrency` pour déterminer s'ils sont différents.|  
|[CComCurrency::operator \*](../Topic/CComCurrency::operator%20*.md)|Cet opérateur permet d'effectuer une multiplication sur un objet `CComCurrency`.|  
|[CComCurrency::operator \*\=](../Topic/CComCurrency::operator%20*=.md)|Cet opérateur permet d'effectuer une multiplication sur un objet `CComCurrency` et de lui assigner le résultat.|  
|[CComCurrency::operator \/](../Topic/CComCurrency::operator%20-1.md)|Cet opérateur permet d'effectuer une division sur un objet `CComCurrency`.|  
|[CComCurrency::operator \/\=](../Topic/CComCurrency::operator%20-=2.md)|Cet opérateur permet d'effectuer une division sur un objet `CComCurrency` et de lui assigner le résultat.|  
|[CComCurrency::operator \+](../Topic/CComCurrency::operator%20+.md)|Cet opérateur permet d'effectuer une addition sur un objet `CComCurrency`.|  
|[CComCurrency::operator \+\=](../Topic/CComCurrency::operator%20+=.md)|Cet opérateur permet d'effectuer une addition sur un objet `CComCurrency` et d'assigner le résultat à l'objet actuel.|  
|[CComCurrency::operator \<](../Topic/CComCurrency::operator%20%3C.md)|Cet opérateur compare deux objets `CComCurrency` pour déterminer le plus petit.|  
|[CComCurrency::operator \<\=](../Topic/CComCurrency::operator%20%3C=.md)|Cet opérateur compare deux objets `CComCurrency` pour déterminer le plus petit ou leur égalité.|  
|[CComCurrency::operator \=](../Topic/CComCurrency::operator%20=.md)|Cet opérateur assigne l'objet `CComCurrency` à une nouvelle valeur.|  
|[CComCurrency::operator \-\=](../Topic/CComCurrency::operator%20-=1.md)|Cet opérateur permet d'effectuer une soustraction sur un objet `CComCurrency` et de lui assigner le résultat.|  
|[CComCurrency::operator \=\=](../Topic/CComCurrency::operator%20==.md)|Cet opérateur compare deux objets `CComCurrency` pour déterminer leur égalité.|  
|[CComCurrency::operator \>](../Topic/CComCurrency::operator%20%3E.md)|Cet opérateur compare deux objets `CComCurrency` pour déterminer le plus grand.|  
|[CComCurrency::operator \>\=](../Topic/CComCurrency::operator%20%3E=.md)|Cet opérateur compare deux objets `CComCurrency` pour déterminer le plus grand ou leur égalité.|  
|[CComCurrency::operator CURRENCY](../Topic/CComCurrency::operator%20CURRENCY.md)|Effectue un cast d'un objet `CURRENCY`.|  
  
### Membres de données publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCurrency::m\_currency](../Topic/CComCurrency::m_currency.md)|Variable `CURRENCY` créée par votre instance de classe.|  
  
## Notes  
 `CComCurrency` est un wrapper pour le type de données **CURRENCY**.  Le type **CURRENCY** est implémenté en tant qu'entier de 8 octets en complément à deux, multiplié par 10 000.  Ceci fournit un nombre à virgule fixe avec 15 chiffres à gauche du séparateur décimal et 4 chiffres à droite.  Le type de données **CURRENCY** est extrêmement utile pour les calculs impliquant des valeurs monétaires ou pour les calculs à virgule fixe où la précision est importante.  
  
 Le wrapper **CComCurrency** implémente des opérations arithmétiques, d'affectation et de comparaison pour ce type à virgule fixe.  Les applications prises en charge ont été sélectionnées pour contrôler les erreurs d'arrondi qui peuvent se produire lors de calculs à virgule fixe.  
  
 L'objet `CComCurrency` permet d'accéder aux nombres figurant de chaque côté du séparateur décimal sous la forme de deux composantes : une partie entière correspondant à la valeur à gauche du séparateur décimal et une partie fractionnaire correspondant à la valeur à droite du séparateur décimal.  La partie fractionnaire est stockée en interne en tant que valeur entière comprise entre \-9999 \(**CY\_MIN\_FRACTION**\) et \+9999 \(**CY\_MAX\_FRACTION**\).  La méthode [CComCurrency::GetFraction](../Topic/CComCurrency::GetFraction.md) retourne une valeur multipliée par un facteur de 10 000 \(**CY\_SCALE**\).  
  
 Quand vous spécifiez les composantes entière et fractionnaire d'un objet **CComCurrency**, n'oubliez pas que la composante fractionnaire est un nombre compris entre 0 et 9999.  Ceci est important dans le cas d'une devise telle que le dollar américain, où les sommes sont exprimées avec seulement deux chiffres significatifs après le séparateur décimal.  Bien que les deux derniers chiffres ne soient pas affichés, ils doivent être pris en compte.  
  
|Valeur|Affectations CComCurrency possibles|  
|------------|-----------------------------------------|  
|$10.50|CComCurrency\(10,5000\) *ou* CComCurrency\(10.50\)|  
|$10.05|CComCurrency\(10,500\) *ou* CComCurrency\(10.05\)|  
  
 Les valeurs **CY\_MIN\_FRACTION**, **CY\_MAX\_FRACTION** et **CY\_SCALE** sont définies dans atlcur.h.  
  
## Configuration requise  
 **En\-tête :** atlcur.h  
  
## Voir aussi  
 [COleCurrency Class](../../mfc/reference/colecurrency-class.md)   
 [CURRENCY](http://msdn.microsoft.com/fr-fr/5e81273c-7289-45c7-93c0-32c1553f708e)   
 [Class Overview](../../atl/atl-class-overview.md)