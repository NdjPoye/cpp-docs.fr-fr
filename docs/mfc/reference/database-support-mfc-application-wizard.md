---
title: "Prise en charge des bases de donn&#233;es, Assistant Application MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.database"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Application MFC, prise en charge des bases de données"
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Prise en charge des bases de donn&#233;es, Assistant Application MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La page Prise en charge des bases de données propose des options vous permettant de spécifier le niveau de prise en charge des bases de données \(plus une source de données, si nécessaire\) pour votre projet.  
  
 **Prise en charge des bases de données**  
 Définit le niveau de prise en charge des bases de données pour votre projet.  
  
|Option|Description|  
|------------|-----------------|  
|**None**|N'offre aucune prise en charge des bases de données.  Il s'agit de l'option par défaut.|  
|**Fichiers d'en\-tête uniquement**|Assure le niveau de base de prise en charge des bases de données pour votre application.<br /><br /> <ul><li>Si vous sélectionnez la prise en charge ODBC sous **Type de client**, l'Assistant Application MFC inclut dans votre projet le fichier d'en\-tête AFXDB.H.  Il ajoute des bibliothèques de liens, mais il ne crée pas de classes spécifiques à la base de données.  Vous pouvez créer des recordsets ultérieurement et les utiliser pour examiner et mettre à jour les enregistrements.</li><li>Si vous sélectionnez la prise en charge OLE DB sous **Type de client**, les fichiers d'en\-tête suivants sont inclus :<br /><br /> <ul><li>ATLBASE.H</li><li>AFXOLEDB.H</li><li>ATLPLUS.H</li></ul></li></ul>|  
|**Vue de base de données sans prise en charge des fichiers**|Inclut les fichiers d'en\-tête de base de données, les bibliothèques de liaison, une vue de l'enregistrement et un recordset. \(Cette option n'est disponible que pour les applications pour lesquelles l'option **Prise en charge de l'architecture Document\/Vue** est sélectionnée dans la page [Type d'application](../../mfc/reference/application-type-mfc-application-wizard.md).\) Cette option inclut une prise en charge des documents, mais pas de prise en charge de la sérialisation.  Si vous choisissez d'inclure une vue de base de données, vous devez spécifier la source des données.|  
|**Vue de base de données avec prise en charge des fichiers**|Inclut les fichiers d'en\-tête de base de données, les bibliothèques de liaison, une vue de l'enregistrement et un recordset. \(Cette option n'est disponible que pour les applications pour lesquelles l'option **Prise en charge de l'architecture Document\/Vue** est sélectionnée dans la page **Type d'application**.\) Cette option permet de prendre en charge la sérialisation des documents, que vous pouvez par exemple utiliser pour mettre à jour un fichier de profil utilisateur.  Les applications de base de données opèrent généralement par enregistrement et non par fichier ; elles n'ont donc pas besoin de la sérialisation.  Il se peut toutefois que vous utilisiez la sérialisation dans un but spécial.  Si vous choisissez d'inclure une vue de base de données, vous devez spécifier la source des données.|  
  
> [!NOTE]
>  Si vous sélectionnez **Vue de base de données sans prise en charge des fichiers** ou **Vue de base de données avec prise en charge des fichiers** sous **Prise en charge des bases de données**, la dérivation de la classe d'affichage change selon la sélection effectuée sous **Type de client**, comme suit :  
  
-   Si vous sélectionnez **ODBC** sous **Type de client**, la classe d'affichage de l'application dérive de [CRecordView](../../mfc/reference/crecordview-class.md).  Cette classe est associée à une classe dérivée de [CRecordset](../../mfc/reference/crecordset-class.md), que l'Assistant Application MFC se charge également de créer.  Cette option permet de générer une application basée sur les formulaires, dans laquelle la vue de l'enregistrement est utilisée pour visualiser et mettre à jour les enregistrements par l'intermédiaire de leur recordset.  
  
-   Si vous sélectionnez **OLE DB** sous **Type de client**, la classe d'affichage dérive de [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md) et est associée à une classe dérivée de [CTable](../../data/oledb/ctable-class.md) ou de [CCommand](../../data/oledb/ccommand-class.md).  
  
 **Type de client**  
 Indique si votre projet utilise des classes OLE DB ou ODBC.  
  
|Option|Description|  
|------------|-----------------|  
|**OLE DB**|Lorsque cette option est sélectionnée, le fait de cliquer sur le bouton **Source de données** appelle l'Assistant **Propriétés des liaisons de données**, qui vous aide à créer une connexion vers une source de données OLE DB.|  
|**ODBC**|Lorsque cette option est sélectionnée, le fait de cliquer sur le bouton **Source de données** appelle l'Assistant **Sélectionner la source de données**, qui vous aide à créer une connexion vers une source de données ODBC.|  
  
 **Source de données**  
 Cliquez sur le bouton **Source de données** pour définir une source de données à l'aide du pilote ou du fournisseur et de la base de données spécifiés.  Si vous sélectionnez OLE DB sous l'option **Type de client**, ce bouton génère l'affichage de la boîte de dialogue **Propriétés des liaisons de données**.  Si vous sélectionnez ODBC sous l'option **Type de client**, ce bouton génère l'affichage de la boîte de dialogue **Sélectionner la source de données**.  Cette option n'est disponible que si vous choisissez d'inclure une vue de base de données dans votre application.  
  
|Option|Description|  
|------------|-----------------|  
|**Propriétés des liaisons de données** \(OLE DB\)|Établit la source de données spécifiée à l'aide du fournisseur OLE DB indiqué.  Vous devez spécifier le fournisseur OLE DB, l'emplacement des données, la source de données, l'ID de connexion et un mot de passe \(facultatif\).  Pour plus d'informations sur cette boîte de dialogue, consultez **Source de données** dans l'[Assistant Consommateur OLE DB ATL](../../atl/reference/atl-ole-db-consumer-wizard.md).|  
|**Sélectionner la source de données** \(ODBC\)|Établit la source de données spécifiée à l'aide du pilote ODBC indiqué.  Vous devez sélectionner un nom de source de données pour pouvoir choisir une table pour la source de données.  L'Assistant lie toutes les colonnes de la table aux variables membres d'une classe dérivée de `CRecordset`.  Pour plus d'informations sur cette boîte de dialogue, consultez **Source de données** dans l'[Assistant Consommateur ODBC MFC](../../mfc/reference/mfc-odbc-consumer-wizard.md).|  
  
> [!NOTE]
>  Dans les versions précédentes, cliquer sur la touche MAJ et sur le bouton **Source de données** ouvrait une boîte de dialogue d'ouverture de fichier pour vous permettre de sélectionner un fichier .udl.  Cette fonctionnalité n'est plus prise en charge.  
  
 **Générer une classe de base de données avec attributs**  
 Disponible uniquement pour le client OLE DB.  Indique si les classes de base de données du projet généré utilisent des attributs.  
  
 **Lier toutes les colonnes**  
 Disponible uniquement pour le client ODBC.  Indique si toutes les colonnes de la table sélectionnée sont dépendantes.  Si vous activez cette case à cocher, toutes les colonnes sont dépendantes ; dans le cas contraire, aucune colonne n'est dépendante et vous devez les lier manuellement dans la classe du recordset.  
  
 **Type**  
 Disponible uniquement pour le client ODBC.  Indique si le recordset est un dynaset ou un instantané, comme décrit dans le tableau ci\-dessous.  
  
|Option|Description|  
|------------|-----------------|  
|**Dynaset**|Spécifie que le recordset est un dynaset.  Un dynaset est le résultat d'une requête qui fournit une vue indexée des données de la base de données interrogée.  Un dynaset ne met en cache qu'un index intégral des données d'origine et permet ainsi d'obtenir de meilleures performances qu'un instantané.  L'index pointe directement vers chaque enregistrement trouvé à la suite d'une requête et indique si un enregistrement est supprimé.  Vous avez également accès aux informations mises à jour dans les enregistrements qui ont fait l'objet de la requête.|  
|Instantané|Spécifie que le recordset est un instantané.  Un instantané est le résultat d'une requête et représente une vue de la base de données à un moment donné.  Tous les enregistrements trouvés à la suite de la requête sont mis en cache, si bien que vous ne voyez pas les modifications apportées aux enregistrements d'origine.|  
  
## Voir aussi  
 [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md)