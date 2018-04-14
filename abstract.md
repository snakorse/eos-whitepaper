摘要：

EOS.IO 软件引入一种新的区块链架构设计，它使得去中心化的应用可以横向和纵向的扩展。这通过实现一个可在其之上构建应用的类似操作系统的架构来实现。该软件提供账户、身份认证、数据库、异步通信和跨众多CPU内核或集群的应用程序调度。由此产生的技术是一个区块链架构，可以最终达到支持每秒百万级交易、免用户手续费，并且在受治理的区块链环境中实现快速便捷的部署和维护去中心化应用。

> **Abstract:**
>
> The EOS.IO software introduces a new blockchain architecture designed to enable vertical and horizontal scaling of decentralized applications. This is achieved by creating an operating system-like construct upon which applications can be built. The software provides accounts, authentication, databases, asynchronous communication, and the scheduling of applications across many of CPU cores or clusters. The resulting technology is a blockchain architecture that may ultimately scale to millions of transactions per second, eliminates user fees, and allows for quick and easy deployment and maintenance of decentralized applications, in the context of a governed blockchain.

**请注意：本白皮书中提到的加密Token指在采用EOS.IO软件构建的区块链之上的加密Token。并不是指与在与EOS token分发有关的以太坊区块链上分发的兼容ERC-20标准的token。**

> **PLEASE NOTE: CRYPTOGRAPHIC TOKENS REFERRED TO IN THIS WHITE PAPER REFER TO CRYPTOGRAPHIC TOKENS ON A LAUNCHED BLOCKCHAIN THAT ADOPTS THE EOS.IO SOFTWARE. THEY DO NOT REFER TO THE ERC-20 COMPATIBLE TOKENS BEING DISTRIBUTED ON THE ETHEREUM BLOCKCHAIN IN CONNECTION WITH THE EOS TOKEN DISTRIBUTION.**

在非用于商业和教育用途的前提下 \(即，除了收取费用或商业目的\)，如果注明原始出处并声明版权，任何人可以在未经允许的情况下使用、复制或发布本白皮书内的任何内容。

> Copyright © 2018 block.one
>
> Without permission, anyone may use, reproduce or distribute any material in this white paper for non-commercial and educational use \(i.e., other than for a fee or for commercial purposes\) provided that the original source and the applicable copyright notice are cited.

**免责声明：**

本EOS.IO技术白皮书第二版仅供参考。block.one不保证本白皮书中所描述的结论的准确性，并且本白皮书仅作为草案。

> **DISCLAIMER:**
>
> This EOS.IO Technical White Paper v2 is for information purposes only. block.one does not guarantee the accuracy of or the conclusions reached in this white paper, and this white paper is provided “as is”. block.one does not make and expressly disclaims all representations and warranties, express, implied, statutory or otherwise, whatsoever, including, but not limited to: \(i\) warranties of merchantability, fitness for a particular purpose, suitability, usage, title or noninfringement; \(ii\) that the contents of this white paper are free from error; and \(iii\) that such contents will not infringe third-party rights. block.one and its affiliates shall have no liability for damages of any kind arising out of the use, reference to, or reliance on this white paper or any of the content contained herein, even if advised of the possibility of such damages. In no event will block.one or its affiliates be liable to any person or entity for any damages, losses, liabilities, costs or expenses of any kind, whether direct or indirect, consequential, compensatory, incidental, actual, exemplary, punitive or special for the use of, reference to, or reliance on this white paper or any of the content contained herein, including, without limitation, any loss of business, revenues, profits, data, use, goodwill or other intangible losses.



