---
title: "DATE Type | Microsoft Docs"
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
  - "DATE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Date (type de données)"
  - "Date (type de données), about Date data type"
  - "Date (type de données), implémenter"
  - "DATE type"
  - "hour values representation"
  - "MFC, date et heure"
ms.assetid: 695853ed-b614-4575-b793-b8c287372038
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DATE Type
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le type de **DATE** est implémenté à l'aide d'un nombre à virgule flottante 8 octets.  Les jours sont représentés par des index de nombre entier démarrant avec le le 30 décembre 1899, minuit comme l'heure zéro.  Les valeurs d'heure sont exprimées comme valeur absolue de la partie fractionnaire du nombre.  Le tableau suivant montre plusieurs dates avec leur type équivalent numérique de **DATE** :  
  
|Date et heure|Représentation|  
|-------------------|--------------------|  
|30 décembre 1899, Minuit|0.00|  
|1er janvier 1900, Minuit|2.00|  
|4 janvier 1900, Minuit|5.00|  
|4 janvier 1900, 6h du matin..|5.25|  
|4 janvier 1900, Midi|5.50|  
|4 janvier 1900, 21h..|5.875|  
  
 Le type de **DATE** , ainsi que la classe d' `COleDateTime` , représente des dates et heures comme ligne de nombres classique.  La classe d' `COleDateTime` contient plusieurs méthodes pour manipuler les valeurs de date, y compris la conversion vers et d'autres formats de date courants.  
  
 Les points suivants doivent être notés lorsque vous utilisez ces formats de date et d'heure dans l'automation :  
  
-   Les dates sont spécifiées dans le temps l'heure locale ; la synchronisation doit être exécutée manuellement l'utilisation des dates dans différents fuseaux horaires.  
  
-   Les types de date ne montrent pas l'heure d'été.  
  
-   La chronologie de date est discontinue pour les valeurs de date moins de 0 \(avant le 30 décembre 1899\).  C'est parce que la partie de nombre entier de la valeur de date est traitée comme étant signée, alors que la partie fractionnaire est traitée comme non signée.  En d'autres termes, la partie de nombre entier de la valeur de date peut être positive ou négative, alors que la partie fractionnaire de la valeur de date est toujours ajoutée à la date logique globale.  La table suivante présente quelques exemples :  
  
|Date et heure|Représentation|  
|-------------------|--------------------|  
|27 décembre 1899, Minuit|\-3.00|  
|28 décembre 1899, Midi|\-2.50|  
|28 décembre 1899, Minuit|\-2.00|  
|29 décembre 1899, Minuit|\-1.00|  
|30 décembre 1899, 18h..|\-0.75|  
|30 décembre 1899, Midi|\-0.50|  
|30 décembre 1899, 6h du matin..|\-0.25|  
|30 décembre 1899, Minuit|0.00|  
|30 décembre 1899, 6h du matin..|0.25|  
|30 décembre 1899, Midi|0.50|  
|30 décembre 1899, 18h..|0.75|  
|31 décembre 1899, Minuit|1.00|  
|1er janvier 1900, Minuit|2.00|  
|1er janvier 1900, Midi|2.50|  
|2 janvier 1900, Minuit|3.00|  
  
> [!CAUTION]
>  Étant donné que le 6h00 du matin est toujours représenté par une valeur fractionnaire 0,25 que l'entier représentant le niveau est positif que \(après le 30 décembre 1899\) ou négatif \(avant le 30 décembre 1899\), une comparaison simple de virgule flottante trierait à tort tout **DATE** représentant le 6h00 du matin sur une date antérieure à 12\/30\/1899 comme *ultérieure à***DATE** représentant le 7h00 du matin ce même niveau.  
  
 Plus d'informations sur les problèmes liés aux types de **DATE** et d' `COleDateTime` se trouvent sous [COleDateTime Class](../atl-mfc-shared/reference/coledatetime-class.md) et [Date and Time: Automation Support](../atl-mfc-shared/date-and-time-automation-support.md).  
  
## Voir aussi  
 [Date and Time](../atl-mfc-shared/date-and-time.md)   
 [COleDateTime Class](../atl-mfc-shared/reference/coledatetime-class.md)