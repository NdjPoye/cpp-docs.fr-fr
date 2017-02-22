---
title: "GetCodeForDllCanUnloadNow | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetCodeForDllCanUnloadNow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForDllCanUnloadNow (méthode)"
ms.assetid: 24ee3ef7-45be-4778-99e8-6df493f0782b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# GetCodeForDllCanUnloadNow
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient le code nécessaire au déchargement de la DLL.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      function GetCodeForDllCanUnloadNow(   
   nLineStart,   
   nLineEnd    
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nLineStart`  
 Numéro de ligne de base zéro du début de la fonction.  
  
 `nLineEnd`  
 Numéro de ligne de base zéro de la fin de la fonction.  
  
## <a name="return-value"></a>Valeur de retour  
 Chaîne contenant le code de déchargement de la DLL.  
  
## <a name="remarks"></a>Notes  
 Appelez cette fonction membre pour récupérer le code nécessaire au déchargement de la DLL. Appel de cette fonction crée une chaîne unique en concaténant les éléments du tableau que vous spécifiez.  
  
 Le tableau suivant présente le code nécessaire au déchargement de la DLL.  
  
|Numéro de ligne|Code|  
|-----------------|----------|  
|0|AFX_MANAGE_STATE(AfxGetStaticModuleState()) ;|  
|1|Si (_AtlModule.GetLockCount() > 0)|  
|2|\treturn S_FALSE ;|  
|3|Retourne S_OK ;|  
  
 Pour chacune des lignes retournées, `GetCodeForDllCanUnloadNow` ajoute une tabulation à gauche (`\t`) et une paire de caractères « CR-LF » (retour chariot - saut de ligne) à droite (`\r\n`).  
  
## <a name="example"></a>Exemple  
  
```  
// Get the lines numbered 1 and 2 above  
GetCodeForDllCanUnloadNow(1, 2)  
  
// returns the following string  
// "\tif (_AtlModule.GetLockCount() > 0)\r\n\t\treturn S_FALSE;\r\n"  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Personnalisation des Assistants C++ à l’aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C++](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d’un Assistant](../ide/designing-a-wizard.md)   
 [GetCodeForDllGetClassObject](../ide/getcodefordllgetclassobject.md)   
 [GetCodeForExitInstance](../ide/getcodeforexitinstance.md)