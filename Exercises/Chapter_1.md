#### Exercise 1.1

```lisp
10
;; Value: 10

(+ 5 3 4)
;; Value: 12

(- 9 1)
;; Value: 8

(/ 6 2)
;; Value: 3

(+ (* 2 4) (- 4 6))
;; Value: 6

(define a 3)
;; Value: a

(define b (+ a 1))
;; Value: b

(+ a b (* a b))
;; Value: 19

(= a b)
;; Value: #f

(if (and (> b a) (< b (* a b)))
    b
    a)
;; Value: 4

(cond ((= a 4) 6)
      ((= b 4) (+ 6 7 a))
      (else 25))
;; Value: 16

(+ 2 (if (> b a) b a))
;; Value: 6

(* (cond ((> a b) a)
         ((< a b) b)
         (else -1))
   (+ a 1))
;; Value: 16
```

#### Exercise 1.2

```lisp
(/ (+ 5
      4
      (- 2 (- 3 (+ 6 (/ 4 5)))))
   (* 3
      (- 6 2)
      (- 2 7)))

;; Value: -37/150
```

#### Exercise 1.3
> **NOTE: 翻译有误, 原题是: returns the sum of the squares of the two larger numbers.**

```lisp
(define (sqr x) (* x x))

(define (sum_of_sqr x y) (+ (sqr x) (sqr y)))

(define (sum_of_two_largest_sqr x y z)
    (if (< x y)
            (if (< x z)
                    (sum_of_sqr y z)
                    (sum_of_sqr x y))
            (if (< y z)
                    (sum_of_sqr x z)
                    (sum_of_sqr x y))))
```

#### Exercise 1.4

```lisp
(define (a-plus-abs-b a b)
   ((if (> b 0) + -) a b))
;; Value: (a + |b|)
;; Value: a加b的绝对值
```

#### Exercise 1.5
