#duplicate() method
loans.duplicated()
  Because the default method returns both complete and incomplete duplicates.

loans.duplicated(subset = 'first_name')
  Because constraining the duplicate rows to the first name lets me find incomplete duplicates as well.

loans.duplicated(subset = ['first_name', 'last_name'], keep = False)
  Because subsetting on consumer metadata and not discarding any duplicate returns all duplicated rows.

loans.duplicated(subset = ['first_name', 'last_name'], keep = 'first')
  Because this drops all duplicates.
  
  ---------
# Find duplicates
duplicates = ride_sharing.duplicated(subset='ride_id', keep=False)

# Sort your duplicated rides
duplicated_rides = ride_sharing[duplicates].sort_values('ride_id')

# Print relevant columns of duplicated_rides
print(duplicated_rides[['ride_id','duration','user_birth_year']])
