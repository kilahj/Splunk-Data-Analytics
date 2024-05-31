# Splunk-Data-Analytics

## Objective

This 3-hour virtual workshop was designed for beginners, and it provided valuable hands-on experience with Splunk. We delved into working with machine data and explored its applications in IT operations, security, and business analytics. 

### Skills Learned
- Set up my own Splunk environment
- Collected and indexed data
- Learned how to perform searches
- Created interactive dashboards for different use cases
  
## Some of the key topics we covered:
- Understanding the value of machine data
- Splunk’s unique approach to data investigation
- Building Splunk apps from scratch
- Adding and searching through data
- Extracting new fields on the fly
- Making dashboards for different needs



## Steps
<img width="540" alt="Screen Shot 2024-05-31 at 11 08 40 AM" src="https://github.com/kilahj/Splunk-Data-Analytics/assets/99774720/3c3d0279-3749-4d96-a83a-62383c1a9404">

<img width="350" alt="Screen Shot 2024-05-31 at 11 09 09 AM" src="https://github.com/kilahj/Splunk-Data-Analytics/assets/99774720/f398b5e6-3dfe-4bce-a8bf-69ad8cbf583e">

> As a splunk power user, my responsibility is to provide insights to users throughout the company


## DevOps team: Show the most common customer operating systems and which web browsers are experiencing the most failures
<img width="1151" alt="Screen Shot 2024-05-31 at 11 11 57 AM" src="https://github.com/kilahj/Splunk-Data-Analytics/assets/99774720/9dfd71e2-d7d4-4491-b0bd-c92ef0d6cf1e">

> Data from Splunk

## IT Operations team: Investigate successful vs unsuccessful web server requests over time
```sh
index=main sourcetype=access_combined | timechart count by status limit=10
```
<img width="1439" alt="Screen Shot 2024-05-30 at 1 32 06 PM" src="https://github.com/kilahj/Splunk-Data-Analytics/assets/99774720/4c753819-0060-4ac8-b7f7-d0d1e5ef27c9">

## DevOps team: Show the most common customer operating systems and which web browsers are experiencing the most failures

```sh
index=main sourcetype=access_combined | top limit=20 platform
```

```sh
index=main sourcetype=access_combined status>=400
| timechart count by useragent limit=5
```
<img width="875" alt="Screen Shot 2024-05-31 at 11 32 46 AM" src="https://github.com/kilahj/Splunk-Data-Analytics/assets/99774720/0dda15a5-99cc-4c6e-94aa-a665930bde4b">




## Business Analytics: Show lost revenue from the website
```sh
index=main sourcetype=access_combined action=purchase status>=400
| lookup product_codes.csv product_id
| timechart sum(product_price)
```
```sh
index=main sourcetype=access_combined action=purchase status>=400
| lookup product_codes.csv product_id
```
<img width="639" alt="Screen Shot 2024-05-31 at 11 32 05 AM" src="https://github.com/kilahj/Splunk-Data-Analytics/assets/99774720/b4fa451a-9f66-4ade-80a9-1bd1914118ec">

## Security and Fraud teams: Show website activity by geographic location
```sh
index=main sourcetype=access_combined| iplocation clientip | geostats count by City
```
<img width="639" alt="Screen Shot 2024-05-31 at 11 32 24 AM" src="https://github.com/kilahj/Splunk-Data-Analytics/assets/99774720/c70c8993-98bb-433a-bf4e-7dbf9dafe771">

## FINAL SPLUNK DASHBOARD
<img width="834" alt="Screen Shot 2024-05-30 at 3 09 19 PM" src="https://github.com/kilahj/Splunk-Data-Analytics/assets/99774720/a868fbc8-e22d-4594-8391-7f5c5e5389ae">
