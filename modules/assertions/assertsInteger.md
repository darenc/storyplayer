---
layout: modules-assertions
title: Integer Assertions
prev: '<a href="../../modules/assertions/assertsDouble.html">Prev: Double Assertions</a>'
next: '<a href="../../modules/assertions/assertsObject.html">Next: Object Assertions</a>'
---

# Integer Assertions

_assertsInteger()_ allows you to test a PHP integer, and to compare it against another PHP integer.

The source code for these actions can be found in the class _DataSift\Storyplayer\Prose\IntegerExpects_.

## doesNotEqual()

Use _$st->assertsInteger()->doesNotEqual()_ to make sure that two integer numbers are not the same.

{% highlight php %}
$expected = 1;
$actual   = 2;
$st->assertsInteger($actual)->doesNotEqual($expected);
{% endhighlight %}

See _[equals()](#equals)_ for a discussion of how this test works.

## equals()

Use _$st->assertsInteger()->equals()_ to make sure that two integer numbers are the same.

{% highlight php %}
$expected = 1;
$actual   = 1;
$st->assertsInteger($actual)->equals($expected);
{% endhighlight %}

If the test fails, Storyplayer's output will show the differences between the two numbers.

## isEmpty()

Use _$st->assertsInteger()->isEmpty()_ to make sure that a variable is empty.

{% highlight php %}
$data = 0;
$st->assertsInteger($data)->isEmpty();
{% endhighlight %}

## isGreaterThan()

Use _$st->assertsInteger()->isGreaterThan()_ to make sure that an integer number is larger than a value you provide.

{% highlight php %}
$data = 2;
$st->assertsInteger($data)->isGreaterThan(1);
{% endhighlight %}

## isGreaterThanOrEqualTo()

Use _$st->assertsInteger()->isGreaterThan()_ to make sure that an integer number is at least a value you provide.

{% highlight php %}
$data = 2;
$st->assertsInteger($data)->isGreaterThanOrEqualTo(1);
{% endhighlight %}

## isInteger()

Use _$st->assertsInteger()->isInteger()_ to make sure that something really is an integer.

{% highlight php %}
$data = 1.1;
$st->assertsInteger($data)->isInteger();
{% endhighlight %}

This is most often used in the [post-test inspection phase](../../stories/post-test-inspection.html) to validate the data in the [checkpoint](../../stories/the-checkpoint.html):

{% highlight php %}
$story->setPostTestInspection(function(StoryTeller $st) {
    // get the checkpoint
    $checkpoint = $st->getCheckpoint();

    // make sure the checkpoint contains
    // the final quantity
    $st->assertsObject($checkpoint)->hasAttribute("quantity");
    $st->assertsInteger($checkpoint->quantity)->isInteger();
});
{% endhighlight %}

## isLessThan()

Use _$st->assertsInteger()->isLessThan()_ to make sure that an integer number is smaller than a value you provide.

{% highlight php %}
$data = 1;
$st->assertsInteger($data)->isLessThan(2);
{% endhighlight %}

## isLessThanOrEqualTo()

Use _$st->assertsInteger()->isLessThanOrEqualTo()_ to make sure that an integer number is no larger than a value you provide.

{% highlight php %}
$data = 1;
$st->assertsInteger($data)->isLessThanOrEqualTo(1);
{% endhighlight %}

## isNotEmpty()

Use _$st->assertsInteger()->isNotEmpty()_ to make sure that an integer number is not empty.

{% highlight php %}
$data = 1;
$st->assertsInteger($data)->isNotEmpty();
{% endhighlight %}

## isNull()

Use _$st->assertsInteger()->isNull()_ to make sure that the PHP variable is actually NULL, rather than an integer number.

{% highlight php %}
$data = null;
$st->assertsInteger($data)->isNull()
{% endhighlight %}

This has been added for completeness; we'd always recommend using _[isInteger()](#isinteger)_ instead of testing for NULL.

## isNotNull()

Use _$st->assertsInteger()->isNotNull()_ to make sure that the PHP variable is not NULL.

{% highlight php %}
$data = 1;
$st->assertsInteger($data)->isNotNull();
{% endhighlight %}

This has been added for completeness; we'd always recommend using _[isInteger()](#isinteger)_ instead of testing for NULL.

## isNotSameAs()

Use _$st->assertsInteger()->isNotSameAs()_ to make sure that two PHP integer numbers are not references to each other.

{% highlight php %}
$data1 = 1;
$data2 = 1;

$st->assertsInteger($data1)->isNotSameAs($data2);
{% endhighlight %}

This has been added for completeness; you'll probably use _[doesNotEqual()](#doesnotequal)_ instead.

## isSameAs()

Use _$st->assertsInteger()->isSameAs()_ to make sure that two PHP integer numbers are references to each other.

{% highlight php %}
$data1 = 1;
$data2 = &$data1;

$st->assertsInteger($data1)->isSameAs($data2);
{% endhighlight %}

This has been added for completeness; you'll probably use _[equals()](#equals)_ instead.