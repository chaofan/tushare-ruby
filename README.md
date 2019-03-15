# tushare-ruby简介

这是Ruby版本的[Tushare](https://github.com/waditu/tushare)。

TuShare是实现对中国A股等股票/期货等金融数据从数据采集、清洗加工到数据存储过程的工具，满足金融量化分析师和学习数据分析的人在数据获取方面的需求，它的特点是数据覆盖范围广，接口调用简单,响应快速。

## 安装

在应用的Gemfile中添加:

```ruby
gem 'tushare'
```

然后运行:

    $ bundle

或者通过以下命令行手动安装:

    $ gem install tushare

## 用法
```ruby
require "tushare"
```
### 行情
```ruby
stock = Tushare::Stock::Trading
stock.get_hist_data('300027') #返回日线，300027是A股代码
stock.get_hist_data('600848', ktype: '5') #返回5分钟钱
stock.get_hist_data("002606", start_date: "2016-02-01", end_date: "2016-03-11") #返回指定时期的K线
stock.get_today_all #一次性获取最近一个日交易日所有股票的交易数据
stock.get_index #获取大盘指数行情
```

### 列表
```ruby
l = Tushare::Stock::Classifying
l.industry_classified #A股板块和成份股 行业块
l.terminated #退市
l.suspended #停牌
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release` to create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

1. Fork it ( https://github.com/[my-github-username]/tushare/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request 


