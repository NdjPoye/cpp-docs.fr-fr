---
title: "Stockage de cha&#238;nes dans le fournisseur OLE&#160;DB | Microsoft Docs"
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
  - "enregistrements utilisateur, modifier"
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Stockage de cha&#238;nes dans le fournisseur OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dans MyProviderRS.h, l'Assistant Fournisseur OLE DB ATL crée un enregistrement utilisateur par défaut appelé `CWindowsFile`.  Pour gérer les deux chaînes, modifiez `CWindowsFile` ou ajoutez votre propre enregistrement utilisateur comme illustré dans le code suivant :  
  
```  
////////////////////////////////////////////////////////////////////////  
class CAgentMan:   
   public WIN32_FIND_DATA  
   DWORD dwBookmark;              // Add this  
   TCHAR szCommand[256];          // Add this  
   TCHAR szText[256];             // Add this  
   TCHAR szCommand2[256];         // Add this  
   TCHAR szText2[256];            // Add this  
  
{  
public:  
BEGIN_PROVIDER_COLUMN_MAP()  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command"), 1, 256, GUID_NULL, CAgentMan, szCommand)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text"), 2, 256, GUID_NULL, CAgentMan, szText)   
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command2"), 3, 256, GUID_NULL, CAgentMan, szCommand2)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text2"),4, 256, GUID_NULL, CAgentMan, szText2)  
END_PROVIDER_COLUMN_MAP()  
   bool operator==(const CAgentMan& am) // This is optional   
   {  
      return (lstrcmpi(cFileName, wf.cFileName) == 0);  
   }  
};  
```  
  
 Les données membres `szCommand` et `szText` représentent les deux chaînes, `szCommand2` et `szText2` fournissant des colonnes supplémentaires le cas échéant.  Les données membres `dwBookmark` ne sont pas nécessaires pour ce fournisseur simple accessible en lecture seule mais sont utilisées ultérieurement pour ajouter une interface `IRowsetLocate` ; consultez [Amélioration du fournisseur simple accessible en lecture seule](../../data/oledb/enhancing-the-simple-read-only-provider.md).  L'opérateur `==` compare des instances \(l'implémentation de cet opérateur est facultative\).  
  
 Une fois cette opération effectuée, le fournisseur est normalement prêt pour la compilation et l'exécution.  Pour tester le fournisseur, vous avez besoin d'un consommateur doté de fonctionnalités correspondantes.  [Implémentation d'un consommateur simple](../../data/oledb/implementing-a-simple-consumer.md) montre comment créer un tel consommateur de test.  Exécutez le consommateur de test avec le fournisseur.  Vérifiez que le consommateur de test récupère les chaînes appropriées à partir du fournisseur lorsque vous cliquez sur le bouton **Exécuter** dans la boîte de dialogue **Consommateur de test**.  
  
 Une fois que vous avez testé avec succès votre fournisseur, vous pouvez le cas échéant améliorer son fonctionnement en implémentant des interfaces supplémentaires.  Un exemple est fourni dans [Amélioration du fournisseur simple accessible en lecture seule](../../data/oledb/enhancing-the-simple-read-only-provider.md).  
  
## Voir aussi  
 [Implémentation d'un fournisseur simple accessible en lecture seule](../../data/oledb/implementing-the-simple-read-only-provider.md)