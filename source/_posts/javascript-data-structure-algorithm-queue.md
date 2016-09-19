---
title: 用 JavaScript 學習資料結構和演算法：佇列（Queue）篇
date: 2016-09-11 22:00:00
tags: JavaScript, ECMAScript2015, ES6, Data Structure, Algorithm, Queue, 資料結構, 演算法, 佇列 
author: kdchang
---

![用 JavaScript 學習資料結構和演算法：佇列（Queue）篇](queue.png)

# 前言
在 CS 江湖上曾傳言：`程式設計 = 資料結構 + 演算法`。在一般的大專院校裡，資料結構（Data Structure）與演算法（Algorithm）幾乎都是電腦科學（Computer Science）和資訊相關科系的基礎必修課，在這些課堂中多半是使用 C/C++ 或是 Java 進行教學，許多初學學生也因為對於這些語言的掌握度不夠，反而迷失在資料結構和演算法的世界裡，然而本系列文章將透過 JavaScript 去學習一些經典的資料結構和演算法。作為一個早期限於瀏覽器端開發的程式語言，現在的 JavaScript 早已不能同日而語，不管是前後端開發、行動端、桌面端、硬體開發等都可以看到它的身影，而 JavaScript 輕量和搭配便利的瀏覽器開發者工具特性也讓學習資料結構和演算法更為有趣！本篇將使用 JavaScript 來介紹佇列（Queue）這個經典的資料結構。

## 什麼是佇列（Queue）？
佇列（Queue）是一種先進先出（First In First Out, FIFO）的有序串列（Ordered List），與堆疊（Stack）後進先出（Last In First Out, LIFO）不同的是佇列（Queue）的新增和刪除元素是發生在不同端，新增元素在尾部、移除元素在頂部，最新加入的元素會從尾部排入。在一般生活中比較常見的例子是電影院排隊買票、小七便利商店排隊付款（當然不能有人想插隊啦），在計算機科學領域佇列（Queue）應用也十分常見，像是印表機列印順序排程（當我們點選列印鍵時，第一個列印文件會先被列印，後續送來的文件會依序列印）或是一般作業系統的工作佇列（job queue）、I/O Buffer 緩衝區，也是透過先進先出來處理。

以下是佇列（Queue）幾個特性：

1. 佇列（Queue）是一組相同性質的元素組合
2. 具有先進先出（First In, First Out, FIFO）特性
3. 新增元素時發生在 Rear 後端
4. 刪除元素時發生在 Front 前端 
5. 新增/刪除（Enqueue/Dequeue 或 Add/Delete）元素是發生在不同端

## 用陣列（Array）實作佇列（Queue）
接下來我們將使用 JavaScript 的一維陣列來實作佇列（Queue），其基本步驟如下：

1. 宣告佇列類別

	```
	function Queue() {
		// 這裡將放置佇列的屬性和方法
	}
	```

2. 宣告一個一維陣列（Array）

	首先我們使用一個一維陣列（Array）當做儲存佇列元素的資料結構，這部份和我們之前提到的堆疊（Stack）類似，只是在佇列新增刪除元素時是在不同端點進行：

	```
	function Queue() {
		let items = [];
	}
	```

3. 建立佇列可用方法（method）

	- enqueue(element)：於佇列尾端新增一個或多個元素

	```
	
	```

	- dequeue()：刪除佇列第一個（頭部）的元素，並返回被移除的元素

	- front()：返回佇列中第一個元素，但佇列本身不作任何更動

	- isEmpty()：如果佇列中不包含任何元素，則返回 `true`，反之返回 `false`
 
	- size()：返回佇列所包含的元素個數，即為返回陣列的 `length`


	完整佇列（Queue）類別：

	```
	function Queue() {
		let items = [];
		this.enqueue = function(element) {
			items.push(element);
		};
		this.dequeue = function() {
			return items.shift();
		};
		this.front = function() {
			return items[0];
		};
		this.isEmpty = function() {
			return items.length == 0;
		};
		this.clear = function() {
			items = [];
		};
		this.size = function() {
			return items.length;
		};
		this.print = function() {
			console.log(items.toString());
		}
	}
	```

	使用 Queue 類別

## 優先級佇列（priority queue）

## 環狀佇列（circular queue）

## 總結

# 延伸閱讀
1. [[Algorithm][C / C++] 佇列(Queue)、環狀佇列(Circular Queue)](https://j101044.wordpress.com/2014/08/19/algorithmc-c-%E4%BD%87%E5%88%97queue/)
2. [佇列(Queue)](http://epaper.gotop.com.tw/pdf/AEE032400.pdf)

(image via [stack-machine](https://igor.io/img/stack-machine/stack-ops.png))

