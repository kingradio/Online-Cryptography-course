# Online Cryptography course

## 第一章.密码学绪论（Introduction）

**1.secure communication**

**2.对称加密**

**3.key kind**

   + single key
   + multi used key

**4.limitation**

**5.密码学的应用**

+ Digital Signature
+ Anonymous communication
+ Anonymous digital cash
+ Secure multi-party computation
+ Privately outscoring computation
+ Zero knowledge proof 

**6.密码学模型的安全性检验**

+ 描述威胁模型
+ 提出框架结构
+ 证明此结构的等价性（已证明结构/已知困难数学问题）

**7.古典密码学**

+ Substitution cypher（e.g. 凯撒密码）——密文攻击
+ Vigener cipher——密文攻击
+ Kotor Machine
+ DES —>AES

##  第二章.流密码（Stream Cypher）

**1.密码**

+ 密码的定义
+ 一次密码本（One Time Pad/OTP）
+ Information theoretic security
  + def
  + OTP
  + Thm

**2.流密码的定义**

+ 伪随机数生成器（Pseudo random generator/PRG）

**3.流密码的安全性**

+ unpredictable
  + ''non-neg ''
  + Def
  + Yao's thm:unpredictable-->secure

+ Shannon Secure
  + Statistics tests
  + Advantage——Adv(PRG)
  + "effe" alg.&&''neg'' Adv.-->secure

+ Semantic Security
  + Def
  + Adv(ss)
    + Adv(ss) <= Adv(PRG)
    + secure PRG --> sem.sec. Stream Cypher

**4.Example**

+ RC4(broken)
+ CSS(for DVD,broken)
  + linear feedback register(LFSR)
+ eStream(nonce)
  + Def
  + Salsa20

## 第三章.分块密码（Block Cipher）

**1.Def**

**2.伪随机函数（Pseudo Random Function/PRF）**

+ Def
+ Secure--indistinguishable
+ Example
  + DES
  + 3DES
  + AES

**3.伪随机置换（Pseudo Random Permutation/PRP）**

+ Def
+ Secure--Adv(PRP)

+ Switching Lemma(Secure PRP-->Secure PRF)

**4.DES & 3DES**

+ Festel Network

  + invertible
  + secure

  + function 
  + S boxes

+ Def

+ Attacks on DES

+ Strenthen on DES（prevent exhaustive attacks）

  + 3DES
  + DESX

**5.AES**

+ Def
+ 实现技巧
+ Attacks

**6.Block Ciphers from PRGs  **

**7.use of PRF and PRPs**

+ One time key
+ multi time key
  + attacks
    + 选择明文攻击（chosen-plaintext attack/CPA）
  + sem.sec.

+ 解决方案
  + nonce
    + CBC with nonce
    + rand ctr-mode with nonce
  + randomized encryption
    + CBC wieh initial vector(IV)
    + rand ctr-mode

# 第四章.信息完整性（Massage Intergrity）

**1.MAC**

**2.Security**

+ Def
+ test
+ Adv(MAC)

**3.construction**

+ Secure PRF=>MAC(short)
  + Thm
+ for long data
  + CBC-MAC
  + NMAC
  + Parralled MAC(PMAC)
    + Def
    + sec.
      + Thm.
    + incremental
  + attacks

+ padding
  + invertible and one-to-one

**4.One Time MAC**

+ Def
  + Adv(MAC)
+ Cater-Wegman MAC(CMAC)
+ HMAC

# 第五章.抗碰撞(Collision-Resistant)

**1.Def**

+ Def
+ Thm:small MACs&&col.res H-->big MAC

**2.Generic birhthday attacks**

+ Thm
+ steps

**3.Hash-Markle-Damgard Paradigm**

+ short Hash->long Hash
  + construction
  + padding
  + security

+ construct short Hash
  + David-Mayer
    + construction
    + security

+ + others
  + Block Cipher inside
  + Hash based on Number theory

**4.防碰撞的MAC——HMAC**

+ Thm
+ attack
+ defense

# 第六章.认证加密(Authenticated Encryption/AE)

**1.Def**

+ ciphertext integrity
+ Adv(CI)

**2.Attack**

+ 选择密文攻击(chosen ciphertaxt attack/CCA)
  + Def
  + test
  + Thm
  + Proof

**3.construction from MACs provides AE**

+ construction
+ noticed
  + Enc-then-MAC(suggest)
  + MAC-then-Enc

+ + standard
    + GCM
    + CCM
    + EAX
  + OCB
    + faster and more simple
    + construciton

**4.TLS**

+ construction
+ data
+ enc and dec

**5.attacks**

+ 针对补齐神谕（padding orcal）
+ on enc. length filed
  + lesson

# 第七章.something left

**1.KDF**

+ def
+ construction
+ 分均匀分布的解决方法
  + extract
    + HMAC
  + PBKDF
    + SHA-256

**2.防范CPA攻击**

+ k与m不成对repeats

**3.Deterministic Encryption Construction**

+ DIV(long)
  + Def
  + security
+ a PRP(short)
  + Thm
  + construction
  + intergrity
+ Tweakable encryption
  + Def
  + construction
    + E(tweak)
    + XTS

**4.format preserving encryption**

# 第八章.密钥交换协议(Key Exchange Protocol)

**1.some unsuggested protocols**

+ n! keys
+ 可信第三方(Trusted Third Party/TTP)

**2.Merkle Puzzle**

+ puzzle
+ construction

**3.Diffie-Helmen**

+ construction
+ attacks
+ addition

**4.Public key encryption**

+ Def
+ sem.sec.
+ construction