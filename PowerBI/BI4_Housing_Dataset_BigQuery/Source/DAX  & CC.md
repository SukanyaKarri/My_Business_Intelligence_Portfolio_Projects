DAX:

YOY\_sales\_Growth=
VAR LatestYear =

    YEAR (MAX( 'DateTable'\[Date]))

VAR CurrentYear =

    CALCULATE (

        \[Total Sales],

        YEAR ( 'DateTable'\[Date] ) = LatestYear

    )



VAR PrevYear =

    CALCULATE (

        \[Total Sales],

        YEAR ( 'DateTable'\[Date] ) = LatestYear - 1

    )



RETURN

DIVIDE ( CurrentYear - PrevYear, PrevYear, 0 )



Total Sales = sum(Housing\[Purchase\_Price])



DateTable = CALENDAR(min('Housing'\[DateOnly]),max('Housing'\[DateOnly]))



CC :
offer price=



DateOnly = DATEVALUE('Housing'\[Date])





DAX: Median Sales Price Change =

VAR latestYear =

    YEAR ( MAX ( Housing\[DateOnly] ) )

VAR CurrMedianPrice =

    MEDIANX (

        FILTER ( Housing, YEAR ( Housing\[DateOnly] ) = latestYear ),

        Housing\[Purchase\_Price]

    )

VAR PrevMedianPrice =

    MEDIANX (

        FILTER ( Housing, YEAR ( Housing\[DateOnly] ) = latestYear - 1 ),

        Housing\[Purchase\_Price]

    )

RETURN

    DIVIDE ( CurrMedianPrice - PrevMedianPrice, PrevMedianPrice, 0 )



UnitsSold\_LastYearQuarter =

CALCULATE(

    DISTINCTCOUNT('Housing'\[House\_Type]),

    FILTER(

        'Housing',

        YEAR('Housing'\[DateOnly]) = YEAR(MAX('Housing'\[DateOnly]))

 \&\&

        QUARTER('Housing'\[DateOnly]) = QUARTER(MAX('Housing'\[DateOnly])))





Last 12 Month Sales = CALCULATE(sum('Housing'\[Purchase\_Price]),

DATESINPERIOD(Housing\[DateOnly],max('Housing'\[DateOnly]),-12,MONTH))





Average price per SQM = AVERAGE('Housing'\[SQM\_Price])



TotalYTD Sales = TOTALYTD(sum(Housing\[Purchase\_Price]),Housing\[DateOnly].\[Date])



YOY\_Sales\_Growth =

var LatestYear=year(max('Housing'\[Date]))

var CurrYear=calculate(\[Total Sales],YEAR('Housing'\[Date])=LatestYear)

var PrevYear=CALCULATE(\[Total Sales],YEAR('Housing'\[Date])=LatestYear-1)



return divide(CurrYear-PrevYear,PrevYear,0)





Sales by Region = CALCULATE(sum('Housing'\[Purchase\_Price]),ALLEXCEPT(Housing,Housing\[Region]))



Offer to SQM Ratio = divide(sum(Housing\[offer price]),sum('Housing'\[SQM]))

