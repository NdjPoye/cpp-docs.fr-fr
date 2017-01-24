---
title: "GetCodeForDllGetClassObject | Microsoft Docs"
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
  - "GetCodeForDllGetClassObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForDllGetClassObject (méthode)"
ms.assetid: 67b61b3b-9784-494f-ba01-17bffa9941ff
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetCodeForDllGetClassObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Récupère le code de l’objet de classe DLL.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      function GetCodeForDllGetClassObject(   
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
 Chaîne contenant le code de mise en route de l’objet de classe.  
  
## <a name="remarks"></a>Notes  
 Appelez cette fonction membre pour récupérer le code de l’objet de classe. Appel de cette fonction crée une chaîne unique en concaténant les éléments du tableau que vous spécifiez.  
  
 Le tableau suivant montre le code pour obtenir le code pour l’objet de classe :  
  
|Numéro de ligne|Code|  
|-----------------|----------|  
|0|AFX_MANAGE_STATE(AfxGetStaticModuleState()) ;|  
|1|Si (S_OK == _AtlModule.GetClassObject (rclsid, riid ppv))|  
|2|\treturn S_OK ;|  
|3|retourner AfxDllGetClassObject (rclsid riid, ppv) ;|  
  
 Pour chacune des lignes retournées, `GetCodeForDllGetClassObject` ajoute une tabulation à gauche (`\t`) et une paire de caractères « CR-LF » (retour chariot - saut de ligne) à droite (`\r\n`).  
  
## <a name="example"></a>Exemple  
  
```  
// Get the lines numbered 1 and 2 above  
GetCodeForDllGetClassObject(1, 2)  
  
// returns the following string  
// "\tif (S_OK == _AtlModule.GetClassObject(rclsid, riid, ppv))\r\n\t\treturn S_OK;\r\n"  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Personnalisation des Assistants C++ à l’aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C++](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d’un Assistant](../ide/designing-a-wizard.md)