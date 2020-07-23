# TABERT: Pretraining for Joint Understanding of Textual and Tabular Data

## Conference
- ACL 2020

## References

- [TaBERT](https://arxiv.org/abs/2005.08314) (ACL 2020)
- [TaBERT github](https://github.com/facebookresearch/TaBERT)

## Summary

- 자연어 외에도 다양한 형태로 정보가 존재할 수 있음: 특히 표는 텍스트라는 Modal을 이용하는 구조화 된 형태의 정보
- Figure 1 이 논문의 핵심
  - 모델의 목적: 테이블의 각 행들을 임베딩 하고 이해를 하자
  - 자연어가 주어졌을 때, 가장 관련있는 행을 뽑아서 하자 !
  - Content Snapshot: 질문과 n-gram이 가장 많이 겹치는 상위 k개의 행 뽑아서 임베딩
  - 질문 내용 [SEP] 칼럼 + 행 내용 ... [SEP] 칼럼 + 행 내용 ... [SEP]
  - Row 간 관계는 어떻게 학습할 수 있나? **Vertical Pooling**
    - 각 행 내 정보끼리 Vertical Attention
    - 질문 내용도 Row에 따라 서로 다르게 임베딩 될 것이기 때문에 Vertical Attention

## Discussion

* 1. 데이터를 공개하지 않았다. 어떻게 재현할 수 있을까? Github markdown을 크롤링해서 활용한다면?
* 2. 지식과 NL을 결합한다는 측면에서 KB와 BERT의 fusion이라는 주제와 맞닿아 있다.
* 3. Query (NL)와 Structred data (Table)를 pre-training으로 결합하는 이 방식이 과연 유효한가?
* 4. Check RyanSQL
