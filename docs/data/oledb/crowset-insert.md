---
title: "CRowset::Insert | Microsoft Docs"
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
  - "ATL.CRowset<TAccessor>.Insert"
  - "CRowset.Insert"
  - "CRowset<TAccessor>.Insert"
  - "CRowset<TAccessor>::Insert"
  - "ATL::CRowset<TAccessor>::Insert"
  - "ATL.CRowset.Insert"
  - "CRowset::Insert"
  - "ATL::CRowset::Insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Insert (méthode)"
ms.assetid: 6a64a1c3-10ac-4296-8685-0fd6fe63a13b
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::Insert
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Créé et initialise une nouvelle ligne en utilisant les données provenant de l'accesseur.  
  
## Syntaxe  
  
```  
  
      HRESULT Insert(   
   int nAccessor = 0,   
   bool bGetHRow = false    
) throw( );  
```  
  
#### Paramètres  
 `nAccessor`  
 \[in\] L'index de l'accesseur à utiliser pour insérer les données.  
  
 *bGetHRow*  
 \[in\] indique si le descripteur de la ligne insérée est extraite.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Cette méthode requiert l'interface facultative `IRowsetChange`, qui peut ne pas être prise en charge chez tous les fournisseurs ; dans ce cas, la méthode retourne **E\_NOINTERFACE**.  Vous devez également définir **DBPROP\_IRowsetChange** sur `VARIANT_TRUE` avant d'appeler **Ouvrir** sur la table ou la commande contenant l'ensemble de lignes.  
  
 L'insertion peut échouer si une ou plusieurs colonnes ne sont pas écrivable.  Modifiez le mappage du curseur pour remédier à cette situation.  
  
## Exemple  
 L'exemple suivant indique comment accéder à une source de données via un ensemble de lignes puis insérer une chaîne à l'aide d'une table dans cet ensemble de lignes.  
  
 En premier lieu, créez une classe de table en insérant un objet ATL dans votre projet.  Par exemple, cliquez avec le bouton droit sur le projet dans le volet de l'espace de travail et sélectionnez **New ATL Object**.  De **Accès aux données**, sélectionnez **Consommateur**.  Créez un objet de consommateur de type **Table**. \(Sélection **Table** crée un ensemble de lignes directement de la table ; sélectionnez **Commande** crée un ensemble de lignes à une commande SQL.\) Sélectionnez une source de données, en spécifiant une table à laquelle accéder à la source de données.  Si vous appelez votre objet **CCustomerTable**du consommateur, vous implémenteriez alors votre code d'insertion comme suit :  
  
 [!code-cpp[NVC_OLEDB_Consumer#10](../../data/oledb/codesnippet/CPP/crowset-insert_1.cpp)]  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)