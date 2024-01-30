#### Sample Data Webhook

```bash
{
  "conversation": {
    _id: '65b37833afe781e84afa001f',
    senderId: 'ae8fa9efb9922bfad0667a9f',
    senderName: 'Shika',
    senderPicture: 'https://cdn.picture.com/image...',
    unreadCount: 100,
    isCompleted: false,
    channelBy: {
      _id: '65b37833afe781e84afa001a',
      channelType: 'whatsapp-unofficial',
    },
    createdBy: {
      _id: '65b37833afe781e84afa001a',
      email: 'shigami.fuuka@gmail.com',
    },
    lastMessage: {
      senderId: 'ae8fa9efb9922bfad0667a9f',
      type: 'text | media | ...',
      statusRead: 'read | pending',
      text: 'Hello',
      sendBy: 'user | sender | bot',
      sendAt: Date,
    },
    firstMessageAt: Date,
    lastMessageFromSenderAt: Date,
    chatSessionId: '65b45833afe781e84afa001f',
    createdAt: Date,
    updatedAt: Date,
  },
  "message": {
    _id: '65b37833afe781e84afa001f',
    conversationId: '65b37833afe781e84afa001a',
    messageId: '5e689dfe124e595210cbe40a',
    senderId: 'ae8fa9efb9922bfad0667a9f',
    text: 'Hello',
    type: 'text | polling | media | product | location | contact | facebook-ad',
    statusRead: 'read | pending',
    sendAt: new Date(),
    isForward: false,
    channelBy: {
      _id: '65b37833afe781e84afa001f',
      channelType: 'whatsapp-unofficial',
    },
    media?: {
      url: 'https://manypage-s3-production.my.id/chats/...',
      type: 'image | video | audio | document | sticker',
      mimetype: 'image/jpeg | video/mp4 ...',
      thumbnail: 'base64-data',
    },
    location?: {
      latitude: '62.23283',
      longitude: '-101.202323',
    },
    contact?: {
      name: 'Shika',
      picture: 'https://cdn.picture.com/...',
      number: '62123422311',
      direct: 'wa.me/62123422311',
    },
    polling?: {
      question: 'ToDo Today',
      options: ['Go to Work', 'Go to Work', 'Go to Work'],
    },
    product?: {
      title: 'Big Brand Hoodie',
      description: 'Big Brand Hoddie with Custom Image',
      productUrl: 'https://prodict.hoddie/big-brand',
      imageUrl: 'https://cdn.image.com/hoodie',
      currency: 'IDR',
      price: '1000000',
    },
    facebookAd?: {
      sourceUrl: 'https://fb.com/hjau312',
      title: 'Facebook Ad',
      thumbnail: 'base64-data',
    },
    mentionMessage?: {
      senderId: 'ae8fa9efb9922bfad0667a9f',
      messageId: '5e689dfe124e595210cbe40a',
      type: 'text | Polling | product | location | contact | facebook-ad | image | video | audio | document | sticker',
      text: 'Hello',
      thumbnail: 'https://cdn.image.com/picture...',
      duration: 10,
      question: 'ToDo Today',
      filename: 'barekraf-doc.pdf',
      contactName: 'Shika',
      contactNumber: '6281234567890',
      contactPicture: 'https://cdn.image.com/image...',
      productName: 'Big Brand Hoodie',
      productPrice: 100000,
      productThumbnail: 'https://cdn.image.com/hoodie',
      locationLatitude: '62.23283',
      locationLongitude: '-101.202323',
      locationThumbnail: 'base64-data',
    },
  }
}
```
