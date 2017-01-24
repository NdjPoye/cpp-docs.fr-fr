---
title: "GetCodeForDllRegisterServer | Microsoft Docs"
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
  - "GetCodeForDllRegisterServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCodeForDllRegisterServer (méthode)"
ms.assetid: 2fe733ad-3f1e-4020-9ce3-68956da7d41d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetCodeForDllRegisterServer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient le code nécessaire pour l’inscription d’un serveur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      function GetCodeForDllRegisterServer(   
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
 Une chaîne contenant le code de l’inscription du serveur  
  
## <a name="remarks"></a>Notes  
 Appelez cette fonction membre pour récupérer le code nécessaire pour l’inscription d’un serveur :  
  
|Numéro de ligne|Code|  
|-----------------|----------|  
|0|AFX_MANAGE_STATE(AfxGetStaticModuleState()) ;|  
|1|_AtlModule.UpdateRegistryAppId(true) ;|  
|2|HRESULT hRes = _AtlModule.RegisterServer(TRUE) ;|  
|3|Si (hRes ! = S_OK)|  
|4|hRes \treturn ;|  
|5|if ( !. COleObjectFactory::UpdateRegistryAll(TRUE))|  
|6|\treturn ResultFromScode(SELFREG_E_CLASS) ;|  
|7|Retourne S_OK ;|  
  
 Pour chacune des lignes retournées, `GetCodeForDllRegisterServer` ajoute une tabulation à gauche (`\t`) et une paire de caractères « CR-LF » (retour chariot - saut de ligne) à droite (`\r\n`).  
  
## <a name="example"></a>Exemple  
  
```  
// Get the lines numbered 2 and 3 above  
GetCodeForDllRegisterServer(2, 3)  
  
// returns the following string  
// "\tHRESULT hRes = _AtlModule.RegisterServer(TRUE);\r\n\tif (hRes != S_OK)\r\n"  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Personnalisation des Assistants C++ à l’aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C++](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d’un Assistant](../ide/designing-a-wizard.md)   
 [GetCodeForDllUnregisterServer](../ide/getcodefordllunregisterserver.md)