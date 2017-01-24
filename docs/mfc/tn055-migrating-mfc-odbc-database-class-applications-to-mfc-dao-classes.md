---
title: "TN055&#160;: Migration des applications de classe de base de donn&#233;es ODBC MFC vers des classes DAO MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.odbc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO (C++), migration"
  - "migrer des applications de bases de données"
  - "migrer des applications de bases de données ODBC"
  - "migration (C++), applications de bases de données ODBC"
  - "ODBC (C++), DAO"
  - "ODBC (classes) (C++), classes DAO"
  - "porter des applications de bases de données vers DAO"
  - "porter des applications de bases de données ODBC vers DAO"
  - "TN055"
ms.assetid: 0f858bd1-e168-4e2e-bcd1-8debd82856e4
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN055&#160;: Migration des applications de classe de base de donn&#233;es ODBC MFC vers des classes DAO MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Dans Visual C\+\+ .NET, les Assistants et l'environnement Visual C\+\+ ne prennent plus en charge DAO \(même si les classes DAO sont incluses et que vous pouvez toujours les utiliser\).  Microsoft vous recommande d'utiliser les [Modèles OLE DB](../data/oledb/ole-db-templates.md) ou [ODBC et MFC](../data/odbc/odbc-and-mfc.md) pour vos nouveaux projets.  Vous ne devez utiliser DAO que dans les applications existantes.  
  
 **Vue d'ensemble**  
  
 Dans de nombreux cas il peut être souhaitable de migrer les applications qui utilisent les classes de la base de données ODBC de MFC aux classes de bases de données DAO de MFC.  Cette note technique détaillera la plupart des différences entre les classes ODBC et DAO de MFC.  Avec les différences à l'esprit, il ne doit pas être très difficile de migrer des applications depuis les classes ODBC vers les classes de MFC si vous le souhaitez.  
  
 **Pourquoi migrer de ODBC vers DAO ?**  
  
 Il y a plusieurs raisons pour lesquelles vous pouvez migrer des applications depuis les classes de base de données ODBC vers les classes de base de données DAO, mais la décision n'est pas nécessairement simple ou évidente.  Une chose à prendre en compte est le fait que le moteur de base de données Microsoft Jet utilisé par DAO peut indiquer une source de données ODBC pour laquelle vous avez un pilote ODBC.  Il peut être plus efficace d'utiliser les classes de base de données ODBC ou d'appeler vous\-même ODBC directement, mais le moteur de base de données Microsoft Jet peut lire des données ODBC.  
  
 Certains cas simples qui rendent la décision d'ODBC\/DAO aisée.  Format par exemple, lorsque vous n'avez besoin que d'accéder aux données dans un format que le moteur pour Microsoft Jet peut afficher directement \(format d'accès, Excel, etc.\) le choix évident consiste à utiliser les classes de base de données DAO.  
  
 Des cas complexes se présentent si vos données existent sur un serveur ou sur plusieurs serveurs.  Dans ce cas, la décision d'utiliser les classes de base de données ODBC ou les classes de base de données DAO est difficile.  Si vous souhaitez effectuer des opérations telles que les jointures hétérogènes \(joindre des données depuis des serveurs dans plusieurs formats comme SQL Server et Oracle\), le moteur de base de données Microsoft Jet effectue la jointure pour vous plutôt que de vous forcer à effectuer le travail nécessaire si vous utilisiez les classes de base de données ODBC ou si vous appeliez ODBC directement.  Si vous utilisez un pilote ODBC qui prend en charge les curseurs de pilote, le meilleur choix pourrait bien être les classes de base de données ODBC.  
  
 Le choix peut être compliqué, c'est pourquoi vous pouvez entrer plusieurs exemples de code pour tester les performances des différentes méthodes données en fonction de vos besoins particuliers.  Cette note technique suppose que vous avez pris la décision de migrer des classes de base de données ODBC vers les classes de base de données DAO.  
  
 **Similarités entre les classes de base de données ODBC et les classes de base de données DAO de MFC**  
  
 La création d'origine des classes ODBC MFC est basé sur le modèle d'objet DAO qui a été utilisé dans Microsoft Access et Microsoft Visual Basic.  Cela signifie qu'il existe de nombreuses fonctionnalités communes aux classes ODBC et de DAO MFC, qui ne seront pas toutes répertoriées dans cette section.  En général les modèles de programmation sont les mêmes.  
  
 Pour mettre en surbrillance des similitudes :  
  
-   Les classes ODBC et de DAO des objets de base de données qui gèrent l'utilisation du système de gestion de base de données sous\-jacent \(SGBD\).  
  
-   Les deux arguments reçoivent des objets recordset qui représente un jeu de résultats de ce SGBD.  
  
-   Les bases de données DAO et les objets recordset sont des membres presque identiques aux classes ODBC.  
  
-   Avec les deux jeux de classes, le code pour extraire des données est identique sauf pour certaines modifications d'objet et de nom de membre.  Les modifications sont nécessaires, mais généralement le processus est un changement de nom simple lorsque vous passez des classes ODBC aux classes DAO.  
  
 Par exemple, dans les deux modèles la procédure pour récupérer des données consiste à créer et ouvrir un objet de base de données, créer et ouvrir un objet recordset, et naviguer \(déplacement\) à travers les données en effectuant certaines opérations.  
  
 **Différences entre les classes ODBC et les classes DAO MFC**  
  
 Les classes DAO incluent plus d'objets et un ensemble plus riche de méthodes, mais cette section détaillera uniquement les différences dans des classes et des fonctionnalités similaires.  
  
 Les différences plus évidentes entre les classes sont probablement les changements de nom pour les classes semblables et les fonctions globales.  La liste suivante présente les changements de nom des objets, des méthodes et des fonctions globales associés aux classes de base de données :  
  
|Classe ou fonction|Équivalent dans les classes DAO MFC|  
|------------------------|-----------------------------------------|  
|`CDatabase`|`CDaoDatabase`|  
|`CDatabase::ExecuteSQL`|`CDaoDatabase::Execute`|  
|`CRecordset`|`CDaoRecordset`|  
|`CRecordset::GetDefaultConnect`|`CDaoRecordset::GetDefaultDBName`|  
|`CFieldExchange`|`CDaoFieldExchange`|  
|`RFX_Bool`|`DFX_Bool`|  
|`RFX_Byte`|`DFX_Byte`|  
|`RFX_Int`|`DFX_Short`|  
|`RFX_Long`|`DFX_Long`|  
||`DFX_Currency`|  
|`RFX_Single`|`DFX_Single`|  
|`RFX_Double`|`DFX_Double`|  
|**RFX\_Date \***|**DFX\_Date** \(basé sur`COleDateTime`\)|  
|`RFX_Text`|`DFX_Text`|  
|`RFX_Binary`|`DFX_Binary`|  
|`RFX_LongBinary`|`DFX_LongBinary`|  
  
 \* La fonction `RFX_Date` est basée sur `CTime` et **TIMESTAMP\_STRUCT**.  
  
 Les modifications majeures aux fonctionnalités qui peuvent affecter votre application et requiert davantage que de simples changements de nom sont répertoriés ci\-dessous.  
  
-   Les constantes et les macros permettant de spécifier que des éléments comme le type ouvert de recordset et les options ouvertes de recordset ont été modifiées.  
  
     Avec les classes ODBC MFC nécessaires pour définir ces options via des macros ou des types énumérés.  
  
     Avec les classes de DAO, DAO fournit la définition de ces options dans un fichier d'en\-tête \(DBDAOINT.H\).  Ce type d'ensemble d'enregistrements est un membre énuméré de `CRecordset`, mais avec DAO il s'agit en fait d'une constante.  Par exemple vous pourriez utiliser **instantané** en spécifiant le type de `CRecordset` dans ODBC mais **DB\_OPEN\_SNAPSHOT** lorsque vous spécifiez le type de `CDaoRecordset`.  
  
-   Le type par défaut de l'ensemble de `CRecordset` est **instantané** tandis que le type par défaut de l'ensemble de `CDaoRecordset` est **dynaset** \(consultez la remarque ci\-dessous pour un problème supplémentaires sur les instantanés de la classe ODBC\).  
  
-   La classe ODBC `CRecordset` comporte une option pour créer un type avant uniquement de recordset.  Dans la classe `CDaoRecordset`, avant uniquement n'est pas un type de recordset, mais plutôt une propriété \(ou une option\) de certains types de jeux d'enregistrements.  
  
-   Un recordset d'ajout uniquement lorsque l'on ouvre un objet `CRecordset` signifiais que les données du recordset peuvent être lues et ajoutées.  Avec l'objet `CDaoRecordset`, l'option " ajout uniquement signifie littéralement que les données du jeu d'enregistrements peuvent être ajoutées \(et non lues\).  
  
-   Les fonctions membres de la transaction des classes ODBC sont membres de `CDatabase` et agissent au niveau de la base de données.  Dans les classes de DAO, les fonctions membres de transaction sont membres d'une classe de niveau supérieur \(`CDaoWorkspace`\) et peuvent impacter plusieurs objets `CDaoDatabase` qui partagent le même espace de travail \(espace de transaction\).  
  
-   La classe d'exception a été modifiée.  Des **CDBExceptions** sont levés dans les classes ODBC et des **CDaoExceptions** le sont dans les classes de DAO.  
  
-   `RFX_Date` utilise des objets `CTime` et **TIMESTAMP\_STRUCT** tandis que **DFX\_Date** utilise `COleDateTime`.  Le `COleDateTime` est presque identique à `CTime`, mais est basé sur un OLE **DATE** 8 octets au lieu d'un `time_t` 4 octets ce qui peut contenir une plage plus grande des données.  
  
    > [!NOTE]
    >  Les instantanés de DAO \(`CDaoRecordset`\) sont en lecture seule alors que les instantanés ODBC \(`CRecordset`\) peuvent être modifiables selon le pilote et l'utilisation de la bibliothèque de curseurs ODBC.  Si vous utilisez la bibliothèque de curseurs, les instantanés `CRecordset` sont modifiables.  Si vous utilisez des pilotes Microsoft du pack de pilote de bureau 3.0 sans bibliothèque de curseurs ODBC, les instantanés de `CRecordset` sont en lecture seule.  Si vous utilisez un autre pilote, consultez la documentation du pilote pour déterminer si les instantanés \(**STATIC\_CURSORS**\) sont en lecture seule.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)