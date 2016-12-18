---
title: "Tests de compatibilit&#233; OLE&#160;DB | Microsoft Docs"
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
  - "test de conformité"
  - "test de conformité (OLE DB)"
  - "fournisseurs OLE DB, tester"
  - "tester les fournisseurs"
  - "tester, fournisseurs OLE DB"
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Tests de compatibilit&#233; OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour rendre les fournisseurs plus homogènes, le kit de développement Data Access SDK contient toute une série de tests de compatibilité OLE DB.  Les tests vérifient tous les aspects du fournisseur et vous garantissent raisonnablement que le fournisseur fonctionnera normalement.  Les tests de compatibilité OLE DB font partie du kit de développement Microsoft Data Access SDK.  Cette section met l'accent sur les mesures que vous devez prendre pour réussir les tests de compatibilité.  Pour plus d'informations sur l'exécution des tests de compatibilité OLE DB, consultez le kit de développement SDK.  
  
## Exécution des tests de compatibilité  
 Dans Visual C\+\+ 6.0, les modèles du fournisseur OLE DB ont ajouté un certain nombre de fonctions de raccordement pour vous permettre de vérifier les valeurs et les propriétés.  La plupart de ces fonctions ont été ajoutées en réaction aux tests de compatibilité.  
  
> [!NOTE]
>  Vous devez ajouter plusieurs fonctions de validation pour que votre fournisseur passe avec succès les tests de compatibilité OLE DB.  
  
 Ce fournisseur requiert deux routines de validation.  La première routine, `CRowsetImpl::ValidateCommandID`, fait partie de votre classe rowset.  Elle est appelée pendant la création du jeu de lignes par les modèles du fournisseur.  L'exemple utilise cette routine pour indiquer aux consommateurs qu'il ne prend pas en charge les index.  Le premier appel est adressé à `CRowsetImpl::ValidateCommandID` \(notez que le fournisseur utilise le typedef **\_RowsetBaseClass** ajouté dans la table d'interface pour `CMyProviderRowset` dans [Prise en charge des signets par le fournisseur](../../data/oledb/provider-support-for-bookmarks.md), ce qui fait que vous n'avez pas besoin de taper une longue ligne d'arguments des modèles\).  Ensuite, retournez **DB\_E\_NOINDEX** si le paramètre d'index est différent de **NULL** \(cela indique que le consommateur souhaite utiliser un index\).  Pour plus d'informations sur les ID de commande, consultez la spécification OLE DB et recherchez **IOpenRowset::OpenRowset**.  
  
 Le code suivant correspond à la routine de validation **ValidateCommandID** :  
  
```  
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
// Class: CMyProviderRowset   
  
HRESULT ValidateCommandID(DBID* pTableID, DBID* pIndexID)  
{  
   HRESULT hr = _RowsetBaseClass::ValidateCommandID(pTableID, pIndexID);  
   if (hr != S_OK)  
      return hr;  
  
   if (pIndexID != NULL)  
      return DB_E_NOINDEX;    // Doesn't support indexes  
  
   return S_OK;  
}  
```  
  
 Les modèles du fournisseur appellent la méthode `OnPropertyChanged` chaque fois que quelqu'un modifie une propriété dans le groupe **DBPROPSET\_ROWSET**.  Si vous souhaitez gérer des propriétés pour d'autres groupes, vous devez les ajouter à l'objet approprié \(autrement dit, les contrôles **DBPROPSET\_SESSION** trouvent place dans la classe `CMyProviderSession`\).  
  
 Le code vérifie d'abord si la propriété est liée à une autre.  Si la propriété est chaînée, il affecte la valeur True à la propriété **DBPROP\_BOOKMARKS**.  L'annexe C de la spécification OLE DB contient des informations sur les propriétés.  Ces informations vous indiquent également si la propriété est chaînée à une autre propriété.  
  
 Vous pouvez également, le cas échéant, ajouter la routine `IsValidValue` à votre code.  Les modèles appellent `IsValidValue` lors des tentatives de définition d'une propriété.  Vous devez substituer cette méthode si vous avez besoin d'un traitement supplémentaire lors de la définition de la valeur d'une propriété.  Vous pouvez avoir l'une de ces méthodes pour chaque propriété définie.  
  
## Problèmes liés aux threads  
 Par défaut, l'Assistant Fournisseur OLE DB de l'Assistant Fournisseur OLE DB ATL génère un code pour que le fournisseur puisse s'exécuter dans un modèle « apartment » \(appartement\).  Si vous essayez d'exécuter ce code avec les tests de compatibilité, vous commencez par obtenir des échecs.  Cette situation s'explique par le fait que Ltm.exe, l'outil utilisé pour exécuter les tests de compatibilité OLE DB, applique par défaut le traitement « Free threaded » \(thread libre\).  Le code de l'Assistant Fournisseur OLE DB applique par défaut le modèle appartement à des fins d'amélioration des performances et de la convivialité.  
  
 Pour remédier à ce problème, vous devez modifier LTM ou le fournisseur.  
  
#### Pour modifier LTM en vue d'une exécution en mode thread appartement  
  
1.  Dans le menu principal de LTM, cliquez sur **Outils**, puis sur **Options**.  
  
2.  Sous l'onglet **Général**, remplacez le modèle de thread **Free Threaded** par **Apartment Threaded**.  
  
 Pour modifier votre fournisseur en vue d'une exécution en mode thread libre :  
  
-   Dans le projet de fournisseur, recherchez toutes les instances de `CComSingleThreadModel` et remplacez\-les par `CComMultiThreadModel`, qui doit se trouver dans les en\-têtes source de données, session et rowset.  
  
-   Dans le fichier .rgs, remplacez le modèle de thread **Apartment** par **Both**.  
  
-   Suivez les règles de programmation correctes pour la programmation en mode thread libre \(c'est\-à\-dire, le verrouillage des accès en écriture\).  
  
## Voir aussi  
 [Techniques avancées du fournisseur](../../data/oledb/advanced-provider-techniques.md)