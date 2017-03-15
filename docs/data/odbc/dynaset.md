---
title: "Feuille de r&#233;ponse dynamique | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bibliothèque de curseurs (ODBC), disponibilité des feuilles de réponse dynamiques"
  - "ODBC (curseurs), curseurs de jeux de clés dans les feuilles de réponse dynamiques"
  - "dynasets"
  - "curseurs de jeux de clés dans les feuilles de réponse dynamiques"
  - "ODBC (bibliothèque de curseurs), dynasets"
  - "ODBC (recordsets), dynasets"
  - "recordsets (C++), dynasets"
ms.assetid: 2867e6be-208e-4fe7-8bbe-b8697cb1045c
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Feuille de r&#233;ponse dynamique
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit les feuilles de réponse dynamiques et traite de leur [disponibilité](#_core_availability_of_dynasets).  
  
> [!NOTE]
>  Cette rubrique s'applique aux classes ODBC MFC, y compris [CRecordset](../../mfc/reference/crecordset-class.md).  Pour plus d'informations sur les feuilles de réponse dynamiques dans les classes DAO, consultez [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  Avec DAO, vous pouvez ouvrir des recordsets de type feuille de réponse dynamique.  
  
 Une « feuille de réponse dynamique » est un recordset comprenant des propriétés dynamiques.  Pendant sa durée de vie, un objet Recordset en mode feuille de réponse dynamique \(appelé généralement une feuille de réponse dynamique\) reste synchronisé avec la source de données de la façon suivante.  Dans un environnement multi\-utilisateur, les autres utilisateurs peuvent modifier ou supprimer des enregistrements de votre feuille de réponse dynamique ou ajouter des enregistrements à la table que représente votre feuille de réponse dynamique.  Les enregistrements que votre application ajoute au recordset ou supprime de celui\-ci sont reflétés dans votre feuille de réponse dynamique.  Les enregistrements ajoutés à la table par d'autres utilisateurs ne sont pas reflétés dans votre feuille de réponse dynamique jusqu'à ce que vous reconstruisiez la feuille de réponse dynamique en appelant sa fonction membre **Requery**.  Lorsque d'autres utilisateurs suppriment des enregistrements, le code MFC ignore les suppressions de votre recordset.  Les modifications des autres utilisateurs sur les enregistrements existants sont reflétées dans votre feuille de réponse dynamique dès que vous atteignez l'enregistrement affecté.  
  
 De même, les modifications que vous apportez aux enregistrements dans une feuille de réponse dynamique sont reflétées dans les feuilles de réponse dynamiques utilisées par d'autres utilisateurs.  Les enregistrements que vous ajoutez ne sont pas reflétés dans les feuilles de réponse dynamiques des autres utilisateurs, sauf si ces derniers interrogent à nouveau leurs feuilles de réponse dynamiques.  Les enregistrements que vous supprimez sont marqués comme « supprimés » dans les recordsets des autres utilisateurs.  Si vous effectuez plusieurs connexions vers la même base de données \(plusieurs objets `CDatabase` \), les recordsets associés à ces connexions ont le même statut que les recordsets des autres utilisateurs.  
  
 Les feuilles de réponse dynamiques sont plus utiles lorsque les données doivent être dynamiques, par exemple dans le cas d'un système de réservation d'une compagnie aérienne.  
  
> [!NOTE]
>  Pour utiliser les feuilles de réponse dynamiques, vous devez posséder un pilote ODBC pour la source de données prenant en charge les feuilles de réponse dynamiques. De plus, la bibliothèque de curseurs ODBC ne doit pas être chargée.  Pour plus d'informations, consultez [Disponibilité des feuilles de réponse dynamiques](#_core_availability_of_dynasets).  
  
 Pour spécifier qu'un recordset est une feuille de réponse dynamique, passez **CRecordset::dynaset** comme premier paramètre à la fonction membre **Open** de votre objet Recordset.  
  
> [!NOTE]
>  Pour les jeux feuilles de réponses dynamiques modifiables, votre pilote ODBC doit prendre en charge les instructions de mise à jour positionnée ou la fonction API ODBC **::SQLSetPos**.  Si ces deux éléments sont pris en charge, MFC utilise **::SQLSetPos** pour une plus grande efficacité.  
  
##  <a name="_core_availability_of_dynasets"></a> Disponibilité des feuilles de réponse dynamiques  
 Les classes de base de données MFC prennent en charge les feuilles de réponse dynamiques si les conditions suivantes sont remplies :  
  
-   La DLL de la bibliothèque de curseurs ODBC ne doit pas être en cours d'utilisation pour cette source de données.  
  
     Si la bibliothèque de curseurs est utilisée, elle masque certaines fonctionnalités du pilote ODBC sous\-jacent, nécessaires pour la prise en charge des feuilles de réponse dynamiques.  Si vous voulez utiliser des feuilles de réponse dynamiques \(et si votre pilote ODBC possède les fonctionnalités requises pour les feuilles de réponse dynamiques, comme décrit dans cette section\), vous pouvez faire en sorte que MFC ne charge pas la bibliothèque de curseurs lorsque vous créez un objet `CDatabase`.  Pour plus d'informations, consultez [ODBC](../../data/odbc/odbc-basics.md) et la fonction membre [OpenEx](../Topic/CDatabase::OpenEx.md) ou [Open](../Topic/CDatabase::Open.md) de la classe `CDatabase`.  
  
     Dans la terminologie ODBC, les feuilles de réponse dynamiques et les instantanés sont désignés par le terme « curseur ».  Un curseur est un mécanisme utilisé pour assurer le suivi de son emplacement dans un recordset.  
  
-   Le pilote ODBC de votre source de données doit prendre en charge les curseurs commandés par un ensemble de valeurs clés.  
  
     Les curseurs commandés par un ensemble de valeurs clés gèrent les données d'une table en obtenant et en stockant un ensemble de clés.  Les clés sont utilisées pour obtenir les données actives d'une table lorsque l'utilisateur affiche un enregistrement particulier.  Pour déterminer si votre pilote fournit cette prise en charge, appelez la fonction API ODBC **::SQLGetInfo** avec le paramètre **SQL\_SCROLL\_OPTIONS**.  
  
     Si vous essayez d'ouvrir une feuille de réponse dynamique sans prise en charge de l'ensemble de valeurs clés, vous obtiendrez `CDBException` avec la valeur de code retournée **AFX\_SQL\_ERROR\_DYNASET\_NOT\_SUPPORTED**.  
  
-   Le pilote ODBC de votre source de données doit prendre en charge l'extraction étendue.  
  
     Le terme « extraction étendue » désigne la possibilité de faire défiler en avant et en arrière les enregistrements résultant de votre requête SQL.  Pour déterminer si votre pilote prend en charge cette fonctionnalité, appelez la fonction API ODBC **::SQLGetFunctions** avec le paramètre **SQL\_API\_SQLEXTENDEDFETCH**.  
  
 Si vous voulez des feuilles de réponse dynamiques modifiables \(ou des instantanés\), votre pilote ODBC doit aussi prendre en charge la fonction API ODBC **::SQLSetPos** ou des mises à jour positionnées.  La fonction **::SQLSetPos** permet à MFC de mettre à jour la source de données sans envoyer d'instructions SQL.  Si cette prise en charge est disponible, MFC l'utilise en priorité pour effectuer des mises à jour par SQL.  Pour déterminer si votre pilote prend en charge **::SQLSetPos**, appelez **::SQLGetInfo** avec le paramètre **SQL\_POS\_OPERATIONS**.  
  
 Les mises à jour positionnées utilisent la syntaxe SQL \(sous la forme **WHERE CURRENT OF** \<nomcurseur\>\) pour identifier une ligne particulière dans la table dans la source de données.  Pour déterminer si votre pilote prend en charge les mises à jour positionnées, appelez **::SQLGetInfo** avec le paramètre **SQL\_POSITIONED\_STATEMENTS**.  
  
 Généralement, les feuilles de réponse dynamiques MFC \(mais pas les recordsets à défilement en avant\) nécessitent un pilote ODBC conforme au niveau 2 d'API.  Si le pilote de votre source de données est conforme au niveau 1 du jeu API, vous pouvez toujours utiliser les instantanés modifiables en lecture seule ainsi que les recordsets à défilement en avant, mais pas les feuilles de réponse dynamiques.  Cependant, un pilote de niveau 1 peut prendre en charge les feuilles de réponse dynamiques s'il prend également en charge l'extraction étendue et les curseurs commandés par un ensemble de valeurs clés.  Pour plus d'informations sur les niveaux de conformité ODBC, consultez [ODBC](../../data/odbc/odbc-basics.md).  
  
> [!NOTE]
>  Si vous voulez utiliser les instantanés et les feuilles de réponse dynamiques, vous devez les baser sur deux objets `CDatabase` distincts \(deux connexions différentes\).  
  
 Contrairement aux instantanés qui utilisent un stockage intermédiaire géré par la bibliothèque de curseurs ODBC, les feuilles de réponse dynamiques extraient directement un enregistrement de la source de données dès que vous le faites apparaître.  Les enregistrements sélectionnés initialement par la feuille de réponse dynamique restent donc synchronisés avec la source de données.  
  
 Pour obtenir la liste des pilotes ODBC contenus dans cette version de Visual C\+\+ et des informations sur l'obtention de pilotes supplémentaires, consultez [Liste de pilotes ODBC](../../data/odbc/odbc-driver-list.md).  
  
## Voir aussi  
 [ODBC \(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)