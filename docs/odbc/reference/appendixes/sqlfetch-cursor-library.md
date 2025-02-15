---
title: "SQLFetch (Cursor Library)"
description: "SQLFetch (Cursor Library)"
author: David-Engel
ms.author: davidengel
ms.date: "01/19/2017"
ms.service: sql
ms.subservice: connectivity
ms.topic: reference
helpviewer_keywords:
  - "SQLFetch function [ODBC], Cursor Library"
---
# SQLFetch (Cursor Library)
> [!IMPORTANT]  
>  This feature will be removed in a future version of Windows. Avoid using this feature in new development work and plan to modify applications that currently use this feature. Microsoft recommends using the driver's cursor functionality.  
  
 This topic discusses the use of the **SQLFetch** function in the cursor library. For general information about **SQLFetch**, see [SQLFetch Function](../../../odbc/reference/syntax/sqlfetch-function.md).  
  
 When the cursor library is used, calls to **SQLFetch** cannot be mixed with calls to either **SQLFetchScroll** or **SQLExtendedFetch**.  
  
 If **SQLFetch** is called with SQL_ATTR_ROW_ARRAY_SIZE set to a value greater than 1, the cursor library will pass the call to the driver. If the driver is an ODBC 2.*x* driver, the rowset size will be ignored and the call to **SQLFetch** will return a single row of data.  
  
 If the cursor library is used with an ODBC 2.*x* driver, a bind offset (as defined by the SQL_ATTR_ROW_BIND_OFFSET_PTR statement attribute) is not used when **SQLFetch** is called.  
  
 When the cursor library is loaded, an application cannot call **SQLFetch** to fetch bookmark columns. The cursor library passes the call to **SQLFetch** through to the driver, but the function calls to enable bookmarks and bind the bookmark column are intercepted by the cursor library.
