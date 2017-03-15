---
title: "Programmation avec CComBSTR (ATL) | Microsoft Docs"
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
  - "classe CComBSTR, programmer avec"
  - "Unicode, utiliser CComBSTR (ATL)"
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Programmation avec CComBSTR (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe [CComBSTR](../atl/reference/ccombstr-class.md) ATL fournit un wrapper autour de le type de données d' `BSTR` .  Pendant qu' `CComBSTR` est un outil utile, il existe plusieurs situations qui requièrent l'avertissement.  
  
-   [Problèmes de conversion](#programmingwithccombstr_conversionissues)  
  
-   [Problèmes de portée](#programmingwithccombstr_scopeissues)  
  
-   [Libérer explicitement l'objet de CComBSTR](#programmingwithccombstr_explicitlyfreeing)  
  
-   [À l'aide de objets de CComBSTR dans les boucles](#programmingwithccombstr_usingloops)  
  
-   [Problèmes de fuite de mémoire](#programmingwithccombstr_memoryleaks)  
  
##  <a name="programmingwithccombstr_conversionissues"></a> Problèmes de conversion  
 Bien que plusieurs méthodes d' `CComBSTR` convertissent automatiquement un argument de chaîne ANSI dans Unicode, les méthodes retournent toujours les chaînes au format Unicode.  Pour convertir la chaîne de sortie vers ANSI, utilisez une classe de conversion ATL.  Pour plus d'informations sur les classes de conversion ATL, consultez [Macros de conversion de chaînes ATL et MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
### Exemple  
 [!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/CPP/programming-with-ccombstr-atl_1.cpp)]  
  
 Si vous utilisez un littéral de chaîne pour modifier un objet d' `CComBSTR` , utilisez des chaînes à caractères larges.  Cela réduira des conversions inutiles.  
  
### Exemple  
 [!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/CPP/programming-with-ccombstr-atl_2.cpp)]  
  
##  <a name="programmingwithccombstr_scopeissues"></a> Problèmes de portée  
 Comme avec n'importe quelle classe polie, `CComBSTR` libère les ressources lorsqu'il est hors de portée.  Si une fonction retourne un pointeur vers la chaîne d' `CComBSTR` , cela peut provoquer des problèmes, car le pointeur référence la mémoire qui a déjà été libérée.  Dans ces cas, utilisez la méthode de **Copier** , comme indiqué ci\-dessous.  
  
### Exemple  
 [!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/CPP/programming-with-ccombstr-atl_3.cpp)]  
  
##  <a name="programmingwithccombstr_explicitlyfreeing"></a> Libérer explicitement l'objet de CComBSTR  
 Il est possible de libérer explicitement la chaîne contenue dans l'objet d' `CComBSTR` avant que l'objet afin portée.  Si la chaîne est libérée, l'objet d' `CComBSTR` est incorrect.  
  
### Exemple  
 [!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/CPP/programming-with-ccombstr-atl_4.cpp)]  
  
##  <a name="programmingwithccombstr_usingloops"></a> À l'aide de objets de CComBSTR dans les boucles  
 Comme la classe d' `CComBSTR` alloue une mémoire tampon afin d'exécuter certaines opérations, telles que l'opérateur d' `+=` ou la méthode de **Ajouter** , il n'est pas recommandé d'exécuter la manipulation de chaînes dans une boucle serrée.  Dans ces situations, `CStringT` offre de meilleures performances.  
  
### Exemple  
 [!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/CPP/programming-with-ccombstr-atl_5.cpp)]  
  
##  <a name="programmingwithccombstr_memoryleaks"></a> Problèmes de fuite de mémoire  
 Obtenir l'adresse d' `CComBSTR` initialisé à une fonction comme paramètre de **\[out\]** provoque une fuite de mémoire.  
  
 Dans l'exemple ci\-dessous, la chaîne allouée pour contenir la chaîne `"Initialized"` est coulée lorsque la fonction `MyGoodFunction` remplace la chaîne.  
  
 [!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/CPP/programming-with-ccombstr-atl_6.cpp)]  
  
 Pour éviter une fuite, appelez la méthode de **Vide** exister sur des objets d' `CComBSTR` avant de passer l'adresse comme paramètre de **\[out\]** .  
  
 Notez que le même code ne provoquerait pas une fuite si le paramètre de la fonction était **\[in, out\]**.  
  
## Voir aussi  
 [Concepts](../atl/active-template-library-atl-concepts.md)   
 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)   
 [wstring](../Topic/wstring.md)   
 [String Conversion Macros](../atl/reference/string-conversion-macros.md)