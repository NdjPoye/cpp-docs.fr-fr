---
title: "Recordset&#160;: lancement d&#39;une nouvelle requ&#234;te sur un recordset (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ODBC (recordsets), soumettre à nouveau des requêtes"
  - "recordsets, soumettre à nouveau des requêtes"
  - "actualiser les recordsets"
  - "Requery (méthode)"
  - "lancer de nouvelles requêtes sur les recordsets"
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Recordset&#160;: lancement d&#39;une nouvelle requ&#234;te sur un recordset (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 La présente rubrique explique comment vous pouvez utiliser un objet recordset pour lancer une nouvelle requête — actualiser une requête — à partir de la base de données et dans quelles circonstances vous pourriez procéder ainsi à l'aide de la fonction membre [Requery](../Topic/CRecordset::Requery.md).  
  
 Les principales raisons pouvant conduire à lancer une nouvelle requête sur un recordset sont les suivantes :  
  
-   Mettre le recordset à jour par rapport aux enregistrements ajoutés par vous\-même ou d'autres utilisateurs et aux enregistrements supprimés par d'autres utilisateurs \(ceux que vous avez vous\-même supprimés sont déjà pris en compte dans le recordset\).  
  
-   Actualiser le recordset en fonction de valeurs de paramètres modifiées.  
  
##  <a name="_core_bringing_the_recordset_up_to_date"></a> Mise à jour du recordset  
 Il arrive fréquemment que vous ayez à lancer une nouvelle requête sur l'objet recordset pour le mettre à jour.  Dans un environnement de base de données multi\-utilisateur, d'autres utilisateurs peuvent effectuer des modifications sur les données pendant la durée de vie de votre recordset.  Pour savoir quand votre recordset reflète les modifications effectuées par d'autres utilisateurs et quand les recordsets des autres utilisateurs reflètent vos propres modifications, consultez [Recordset : mise à jour des enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) et [Feuille de réponse dynamique](../../data/odbc/dynaset.md).  
  
##  <a name="_core_requerying_based_on_new_parameters"></a> Lancement d'une nouvelle requête à l'aide de nouveaux paramètres  
 Une autre utilisation fréquente, et également importante, de [Requery](../Topic/CRecordset::Requery.md) consiste à sélectionner un nouvel ensemble d'enregistrements à partir de valeurs de paramètres modifiées.  
  
> [!TIP]
>  La requête s'effectue probablement encore plus vite si vous appelez **Requery** avec des valeurs de paramètres modifiées plutôt que si vous appelez à nouveau la fonction **Open**.  
  
##  <a name="_core_requerying_dynasets_vs.._snapshots"></a> Actualisation de feuilles de réponse dynamiques contre instantanés  
 Comme les feuilles de réponse dynamiques sont censées présenter un ensemble d'enregistrements avec des données dynamiques et mises à jour, il arrive fréquemment que vous lanciez de nouvelles requêtes si vous voulez prendre en compte les ajouts effectués par les autres utilisateurs.  D'un autre côté, les instantanés sont utiles car vous pouvez vous fier à leur contenu statique lorsque vous préparez des états, calculez des totaux, etc.  Cependant, vous souhaiterez parfois lancer une nouvelle requête sur un instantané.  Dans un environnement multi\-utilisateur, les données des instantanés risquent de ne plus être synchronisées avec la source de données suite aux modifications de la base de données par d'autres utilisateurs.  
  
#### Pour lancer une nouvelle requête sur un objet recordset  
  
1.  Appelez la fonction membre [Requery](../Topic/CRecordset::Requery.md) de l'objet.  
  
 Autre solution, fermez le recordset original et réouvrez\-le.  Dans les deux cas, le nouveau recordset représente l'état courant de la source de données.  
  
 Pour obtenir un exemple, consultez [Vues des enregistrements : remplissage d'une zone de liste à partir d'un second recordset](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).  
  
> [!TIP]
>  Pour optimiser les performances de **Requery**, évitez de modifier le [filtre](../../data/odbc/recordset-filtering-records-odbc.md) ou le [tri](../../data/odbc/recordset-sorting-records-odbc.md) du recordset.  Modifiez uniquement la valeur du paramètre avant d'appeler **Requery**.  
  
 Si l'appel de **Requery** échoue, vous pouvez procéder à une nouvelle tentative pour que votre application se termine normalement.  L'appel de **Requery** ou **Open** peut échouer pour diverses raisons.  Une erreur réseau a pu se produire ; ou bien, lors de l'appel, les données existantes ont été libérées mais, avant même que les nouvelles données ne soient accessibles, un autre utilisateur a pu obtenir un accès exclusif ou bien la table dont votre recordset dépend a été supprimée.  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : liaison dynamique de colonnes de données \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [Recordset : création et fermeture de recordsets \(ODBC\)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)