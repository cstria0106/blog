---
title: "Starlight: Fast Container Provisioning on the Edge and over the WAN"
date: 2023-02-20T16:10:51+09:00
draft: true
categories: ["Paper reading"]
tags: ["Cloud", "Network"]
---

# Background

Container 기술은 현재 널리 사용되고 있다. Container는 link bandwidth가 크고 latency가 작은 cloud 환경에서 사용하도록 만들어졌다. 그러나 점점 mobile, edge와 같이 link bandwidth나 latency가 제한적인 환경[^1]에서도 널리 사용되고 있다. 이에 따라 edge 환경에서도 배포를 최적화 하는 것이 Challenge가 되었다.

따라서 이 논문의 저자는 container의 배포 protocol을 다시 디자인하여 3배 빠르고, 5%의 storage overhead만 존재하는 새로운 solution인 starlight를 제시하였다.

Starlight는 [Github](https://github.com/mc256/starlight)를 통해 소스코드가 공개되어 있다.

# Introduction

[^1]: local datacenter에 배포된 FaaS runtime을 예로 들 수 있다. 이런 경우에는 provisioning time이 직접적으로 사용자 경험에 영향을 미친다.
