---
title: "Recordset&#160;: cr&#233;ation et fermeture de recordsets (ODBC) | Microsoft Docs"
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
  - "ODBC (recordsets), fermer"
  - "ODBC (recordsets), créer"
  - "ODBC (recordsets), ouvrir"
  - "recordsets, fermer"
  - "recordsets, créer"
  - "recordsets, ouvrir"
ms.assetid: 8d2aac23-4396-4ce2-8c60-5ecf1b360d3d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset&#160;: cr&#233;ation et fermeture de recordsets (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 Pour utiliser un recordset, construisez un objet recordset et appelez sa fonction membre **Open** pour exécuter la requête du recordset et sélectionner les enregistrements.  Lorsque vous avez fini d'utiliser le recordset, fermez l'objet et supprimez\-le.  
  
 Cette rubrique explique :  
  
-   [quand et comment créer un objet recordset](#_core_creating_recordsets_at_run_time) ;  
  
-   [quand et comment qualifier le comportement du recordset en le paramétrant, le filtrant, le triant ou le verrouillant](#_core_setting_recordset_options) ;  
  
-   [quand et comment fermer un objet recordset](#_core_closing_a_recordset).  
  
##  <a name="_core_creating_recordsets_at_run_time"></a> Création de recordsets à l'exécution  
 Avant de créer les objets recordset dans votre programme, vous écrivez généralement les classes de recordset propres à l'application.  Pour plus d'informations sur cette étape préliminaire, consultez [Ajout d'un consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Ouvrez un objet feuille de réponse dynamique ou instantané lorsque vous devez sélectionner des enregistrements à partir d'une source de données.  Le type d'objet à créer dépend de votre utilisation des données dans l'application et de la prise en charge assurée par le pilote ODBC.  Pour plus d'informations, [Feuille de réponse dynamique](../../data/odbc/dynaset.md) et [Instantané](../../data/odbc/snapshot.md).  
  
#### Pour ouvrir un recordset  
  
1.  Construisez l'objet de la classe dérivée de `CRecordset`.  
  
     Vous pouvez construire l'objet sur le tas ou sur le frame de pile d'une fonction.  
  
2.  Modifiez, le cas échéant, le comportement par défaut du recordset.  Pour connaître les options disponibles, consultez [Définition des options du recordset](#_core_setting_recordset_options).  
  
3.  Appelez la fonction membre [Open](../Topic/CRecordset::Open.md) de l'objet.  
  
 Dans le constructeur, passez un pointeur à un objet de `CDatabase`ou la valeur **NULL** pour utiliser un objet temporaire de base de données que l'infrastructure construit et ouvre en fonction de la chaîne de connexion retournée par la fonction membre [GetDefaultConnect](../Topic/CRecordset::GetDefaultConnect.md).  L'objet `CDatabase` peut déjà être connecté à une source de données.  
  
 L'appel de **Open** utilise SQL pour sélectionner les enregistrements de la source de données.  Le premier enregistrement sélectionné \(s'il en existe\) constitue l'enregistrement courant.  Les valeurs des champs de cet enregistrement sont stockées dans les membres de données de type champ de l'objet recordset.  Si des enregistrements ont été sélectionnés, les deux fonctions membres `IsBOF` et `IsEOF` retournent 0.  
  
 Dans l'appel de [Open](../Topic/CRecordset::Open.md), vous pouvez :  
  
-   Indiquer si le recordset est une feuille de réponse dynamique ou un instantané.  Par défaut, les recordsets sont ouverts en tant qu'instantanés.  Vous pouvez aussi définir un recordset en avant seulement \(forward\-only\), si vous voulez faire défiler les enregistrements l'un après l'autre sans revenir en arrière.  
  
     Par défaut, un recordset utilise le type par défaut stocké dans le membre **m\_nDefaultType** du membre de données de `CRecordset`.  Les Assistants écrivent le code nécessaire à l'initialisation du membre **m\_nDefaultType** avec le type de recordset sélectionné dans l'Assistant.  Au lieu d'accepter cette valeur par défaut, vous pouvez utiliser un autre type de recordset.  
  
-   Définir une chaîne pour remplacer l'instruction SQL par défaut **SELECT** que le recordset construit.  
  
-   Indiquer si le recordset est en lecture seule ou en ajout seul.  Les recordsets permettent une mise à jour complète par défaut, mais vous pouvez n'autoriser que l'ajout de nouveaux enregistrements ou interdire toutes les mises à jour.  
  
 L'exemple suivant montre comment ouvrir un objet instantané en lecture seule de la classe `CStudentSet`, laquelle est propre à l'application :  
  
```  
// Construct the snapshot object  
CStudentSet rsStudent( NULL );  
// Set options if desired, then open the recordset  
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))  
    return FALSE;  
// Use the snapshot to operate on its records...  
```  
  
 Après l'appel de **Open**, utilisez les fonctions membres et les membres de données de l'objet pour manipuler les enregistrements.  Dans certains cas, il se peut que vous souhaitiez lancer une nouvelle requête ou actualiser le recordset pour inclure les modifications intervenues sur la source de données.  Pour plus d'informations, consultez [Recordset : lancement d'une nouvelle requête sur un recordset \(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md).  
  
> [!TIP]
>  La chaîne de connexion que vous utilisez pendant le développement peut ne pas être identique à celle dont les utilisateurs finaux ont besoin.  Pour obtenir des suggestions sur la généralisation de votre application sous cet aspect, consultez [Source de données : Gestion des connexions \(ODBC\)](../../data/odbc/data-source-managing-connections-odbc.md).  
  
##  <a name="_core_setting_recordset_options"></a> Définition des options du recordset  
 Après avoir construit votre objet recordset et avant d'appeler **Open** pour sélectionner les enregistrements, il se peut que vous souhaitiez définir certaines options pour contrôler le comportement du recordset.  Pour l'ensemble des recordsets, vous pouvez :  
  
-   définir un [filtre](../../data/odbc/recordset-filtering-records-odbc.md) pour limiter le nombre d'enregistrements sélectionnés ;  
  
-   définir un ordre de [tri](../../data/odbc/recordset-sorting-records-odbc.md) pour les enregistrements ;  
  
-   définir des [paramètres](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) afin de pouvoir sélectionner des enregistrements à l'aide des informations fournies ou calculées lors de l'exécution.  
  
 Vous pouvez aussi définir l'option suivante si les conditions sont remplies :  
  
-   Si le recordset est modifiable et prend en charge les options de verrouillage, vous pouvez définir la méthode de [verrouillage](../../data/odbc/recordset-locking-records-odbc.md) utilisée pour les mises à jour.  
  
> [!NOTE]
>  Pour influer sur la sélection des enregistrements, vous devez définir ces options avant d'appeler la fonction membre **Open**.  
  
##  <a name="_core_closing_a_recordset"></a> Fermeture d'un recordset  
 Lorsque vous avez fini d'utiliser votre recordset, vous devez le supprimer et désallouer sa mémoire.  
  
#### Pour fermer un recordset  
  
1.  Appelez sa fonction membre [Close](../Topic/CRecordset::Close.md).  
  
2.  Supprimez l'objet recordset.  
  
     Si vous l'avez déclaré sur le frame de pile d'une fonction, l'objet est supprimé automatiquement quand il devient hors de portée.  Sinon, utilisez l'opérateur **delete**.  
  
 La fonction **Close** libère le handle **HSTMT** du recordset.  Elle ne supprime pas l'objet C\+\+.  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : défilement \(ODBC\)](../../data/odbc/recordset-scrolling-odbc.md)   
 [Recordset : ajout, modification et suppression d'enregistrements \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)