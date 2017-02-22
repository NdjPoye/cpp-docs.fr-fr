---
title: "CFileTime Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CFileTime"
  - "CFileTime"
  - "ATL.CFileTime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileTime class"
  - "shared classes, CFileTime"
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CFileTime Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour gérer les valeurs de date et d'heure associées à un fichier.  
  
## Syntaxe  
  
```  
  
   class CFileTime :   
public FILETIME  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileTime::CFileTime](../Topic/CFileTime::CFileTime.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileTime::GetCurrentTime](../Topic/CFileTime::GetCurrentTime.md)|Appelez cette fonction statique pour récupérer un objet d' `CFileTime` qui représente la date système et l'heure actuelles.|  
|[CFileTime::GetTime](../Topic/CFileTime::GetTime.md)|Appelez cette méthode pour récupérer l'heure de l'objet d' `CFileTime` .|  
|[CFileTime::LocalToUTC](../Topic/CFileTime::LocalToUTC.md)|Appelez cette méthode pour convertir une heure de fichiers local à une heure du fichier selon le temps universel coordonné \(UTC\).|  
|[CFileTime::SetTime](../Topic/CFileTime::SetTime.md)|Appelez cette méthode pour définir la date et l'heure stockée par l'objet d' `CFileTime` .|  
|[CFileTime::UTCToLocal](../Topic/CFileTime::UTCToLocal.md)|Appelez cette méthode pour convertir le temps selon le temps universel coordonné \(UTC\) au temps de fichiers local.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileTime::operator \-](../Topic/CFileTime::operator%20-.md)|Cet opérateur est utilisé pour exécuter la soustraction sur un objet d' `CFileTime` ou d' `CFileTimeSpan` .|  
|[CFileTime::operator \!\=](../Topic/CFileTime::operator%20!=.md)|Cet opérateur compare deux objets d' `CFileTime` pour l'inégalité.|  
|[CFileTime::operator \+](../Topic/CFileTime::operator%20+.md)|Cet opérateur est utilisé pour exécuter l'ajout d'un objet d' `CFileTimeSpan` .|  
|[CFileTime::operator \+\=](../Topic/CFileTime::operator%20+=.md)|Cet opérateur est utilisé pour exécuter l'ajout d'un objet d' `CFileTimeSpan` et assigner le résultat à l'objet actuel.|  
|[CFileTime::operator \<](../Topic/CFileTime::operator%20%3C.md)|Cet opérateur compare deux objets d' `CFileTime` pour déterminer les moins.|  
|[CFileTime::operator \<\=](../Topic/CFileTime::operator%20%3C=.md)|Cet opérateur compare deux objets d' `CFileTime` pour déterminer l'égalité ou les moins.|  
|[CFileTime::operator \=](../Topic/CFileTime::operator%20=.md)|l'opérateur d'assignation.|  
|[CFileTime::operator \-\=](../Topic/CFileTime::operator%20-=.md)|Cet opérateur est utilisé pour exécuter la soustraction sur un objet d' `CFileTimeSpan` et assigner le résultat à l'objet actuel.|  
|[CFileTime::operator \=\=](../Topic/CFileTime::operator%20==.md)|Cet opérateur compare deux objets d' `CFileTime` d'égalité.|  
|[CFileTime::operator \>](../Topic/CFileTime::operator%20%3E.md)|Cet opérateur compare deux objets d' `CFileTime` pour déterminer le plus grand.|  
|[CFileTime::operator \>\=](../Topic/CFileTime::operator%20%3E=.md)|Cet opérateur compare deux objets d' `CFileTime` pour déterminer l'égalité ou le plus grand.|  
  
### Constantes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileTime::Day](../Topic/CFileTime::Day.md)|Une donnée membre static stockant le nombre par 100 intervalles de nanoseconde qui composent un jour.|  
|[CFileTime::Hour](../Topic/CFileTime::Hour.md)|Une donnée membre static stockant le nombre par 100 intervalles de nanoseconde qui composent une heure.|  
|[CFileTime::Millisecond](../Topic/CFileTime::Millisecond.md)|Une donnée membre static stockant le nombre par 100 intervalles de nanoseconde qui composent une milliseconde.|  
|[CFileTime::Minute](../Topic/CFileTime::Minute.md)|Une donnée membre static stockant le nombre par 100 intervalles de nanoseconde qui composent une minute.|  
|[CFileTime::Second](../Topic/CFileTime::Second.md)|Une donnée membre static stockant le nombre par 100 intervalles de nanoseconde qui composent une seconde.|  
|[CFileTime::Week](../Topic/CFileTime::Week.md)|Une donnée membre static stockant le nombre par 100 intervalles de nanoseconde qui composent une semaine.|  
  
## Notes  
 Cette classe fournit des méthodes pour gérer les valeurs de date et d'heure associées à la création, l'accès et la modification des fichiers.  Les méthodes et les données de cette classe sont fréquemment utilisées avec les objets d' `CFileTimeSpan` , qui traitent les valeurs d'heure connexes.  
  
 La valeur de date et d'heure est stockée en tant que valeur 64 bits représentant le nombre par 100 intervalles de nanoseconde depuis le 1er janvier 1601.  Il s'agit du format de \(UTC\) de temps universel coordonné.  
  
 Les variables membres const statiques suivantes sont fournies pour simplifier les calculs :  
  
|Variable membre|Nombre par 100 intervalles de nanoseconde|  
|---------------------|-----------------------------------------------|  
|Milliseconde|10,000|  
|Seconde|Milliseconde \* 1.000|  
|Minute|Deuxièmement \* 60|  
|Heure|\* 60 Minute|  
|Jour|Heure \* 24|  
|Semaine|Jour \* 7|  
  
 **Note** tous les systèmes de fichiers peut création d'enregistrement et l'heure du dernier accès et tous les systèmes de fichiers stocker de la même façon.  Par exemple, dans le système de fichiers FAT Windows NT, l'heure de création a une résolution de 10 millisecondes, le temps d'écriture a une résolution de 2 secondes, et le temps d'accès a une résolution de 1 jours \(la date d'accès\).  Sur NTFS, le temps d'accès a une résolution de 1 heure.  En outre, GROS temps d'enregistrements sur le disque en millisecondes temps heure locale, mais d'enregistrements NTFS sur le disque dans l'.  Pour plus d'informations, consultez [heures du fichier](http://msdn.microsoft.com/library/windows/desktop/ms724290).  
  
## Hiérarchie d'héritage  
 `FILETIME`  
  
 `CFileTime`  
  
## Configuration requise  
 **Header:** atltime.h  
  
## Voir aussi  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTimeSpan Class](../../atl-mfc-shared/reference/cfiletimespan-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)