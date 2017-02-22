---
title: "Param&#232;tres de sortie | Microsoft Docs"
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
  - "OLE DB, procédures stockées"
  - "appels de procédure"
  - "appels de procédure, procédures stockées"
  - "procédures stockées, appeler"
  - "procédures stockées, paramètres"
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Param&#232;tres de sortie
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'appel d'une procédure stockée est similaire à l'appel d'une commande SQL.  La principale différence est que les procédures stockées utilisent des paramètres de sortie et des valeurs de retour.  
  
 Dans la procédure stockée suivante, le premier point d'interrogation « ? » correspond à la valeur de retour \(phone\) et le deuxième point d'interrogation « ? » au paramètre d'entrée \(name\) :  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }")  
```  
  
 Vous spécifiez les paramètres d'entrée et de sortie dans le mappage de paramètres :  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)  
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter  
END_PARAM_MAP()  
```  
  
 Votre application doit gérer la sortie retournée à partir des procédures stockées.  Différents fournisseurs OLE DB retournent des paramètres de sortie et des valeurs de retour à différents moments pendant le traitement des résultats.  Par exemple, le fournisseur Microsoft OLE DB pour SQL Server \(SQLOLEDB\) ne fournit des paramètres de sortie et des codes de retour qu'une fois que le consommateur a récupéré ou annulé les jeux de résultats retournés par la procédure stockée.  La sortie est retournée dans le dernier paquet TDS provenant du serveur.  
  
## Nombre de lignes  
 Si vous utilisez les modèles du consommateur OLE DB pour exécuter une procédure stockée qui possède des paramètres de sortie, le nombre de lignes n'est défini qu'à la fermeture du jeu de lignes.  
  
 Prenons l'exemple d'une procédure stockée dotée d'un jeu de lignes et d'un paramètre de sortie :  
  
```  
create procedure sp_test  
   @_rowcount integer output  
as  
   select top 50 * from test  
   @_rowcount = @@rowcount  
return 0  
```  
  
 Le paramètre de sortie @\_rowcount indique le nombre de lignes effectivement retournées à partir de la table de test.  Toutefois, cette procédure stockée limite le nombre de lignes à un maximum de 50.  Par exemple, s'il y avait 100 lignes dans le test, le compteur de ligne serait 50 \(parce que ce code extrait uniquement les 50 lignes supérieures\).  S'il y avait uniquement 30 lignes dans la table, le compteur de ligne serait 30.  Vous devez appeler **Close** ou **CloseAll** pour remplir l'outparameter avant d'extraire sa valeur.  
  
## Voir aussi  
 [Utilisation des procédures stockées](../../data/oledb/using-stored-procedures.md)