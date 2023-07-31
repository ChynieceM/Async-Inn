Async-Inn

Chyniece Matthews

1. HotelLocation - This table is used to track the different hotel locations.
Id: (Primary Key) A unique identifier for each hotel location.
Name: The name of the hotel location.
City: The city where the hotel is located.
State: The state where the hotel is located.
Address: The address of the hotel.
PhoneNumber: The phone number of the hotel.

2. HotelRoom - This table is used to track the rooms in a particular hotel.
Id: (Primary Key) A unique identifier for each hotel room.
HotelId: (Foreign Key) The unique identifier of the hotel where the room is located, linking to HotelLocation.Id.
RoomId: (Foreign Key) The unique identifier of the room type, linking to Rooms.Id.
PetFriendly: A boolean value indicating whether the room is pet-friendly.
Price: The price of the room.

3. Rooms - This table is used to track the different room types/layouts.
Id: (Primary Key) A unique identifier for each room type.
Name: The name of the room type (e.g., "Seahawks Snooze", "Restful Rainier").

4. RoomAmenity - This table is a join table that connects Rooms and Amenities and shows what amenities each room type has.
RoomId: (Composite Key) The unique identifier of the room type, linking to Rooms.Id.
AmenityId: (Composite Key) The unique identifier of the amenity, linking to Amenities.Id.

5. Amenities - This table is used to track the different amenities.
Id: (Primary Key) A unique identifier for each amenity.
Name: The name of the amenity (e.g., "air conditioning", "coffee maker").
The relationships between these tables would be:

HotelLocation to HotelRoom: One-to-many, as each hotel location can have multiple rooms.
HotelRoom to Rooms: Many-to-one, as each hotel room is of a specific room type.
Rooms to RoomAmenity: One-to-many, as each room type can have multiple amenities.
RoomAmenity to Amenities: Many-to-one, as each amenity can be associated with multiple room types.
The RoomAmenity table is a pure join table as it connects Rooms and Amenities. This ERD also includes an enum, which could be used for Amenities.Name, as there would likely be a set list of amenity options.

